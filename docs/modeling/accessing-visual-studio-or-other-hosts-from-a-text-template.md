---
title: テキスト テンプレートから Visual Studio またはその他のホストへのアクセス
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 752b9d9e69eee26f267927f03c4b83c68740100b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652359"
---
# <a name="access-visual-studio-or-other-hosts-from-a-text-template"></a>テキストテンプレートから Visual Studio またはその他のホストにアクセスする

テキストテンプレートでは、テンプレートを実行するホストによって公開されているメソッドとプロパティを使用できます。 ホストの例として、Visual Studio があります。

> [!NOTE]
> ホストメソッドとプロパティは、通常のテキストテンプレートでは使用できますが、*前処理*されたテキストテンプレートでは使用できません。

## <a name="obtain-access-to-the-host"></a>ホストへのアクセスを取得する

ホストにアクセスするには、`template` ディレクティブで `hostspecific="true"` を設定します。 [ITextTemplatingEngineHost](/previous-versions/visualstudio/visual-studio-2012/bb126505(v=vs.110))型の `this.Host` を使用できるようになりました。 [ITextTemplatingEngineHost](/previous-versions/visualstudio/visual-studio-2012/bb126505(v=vs.110))型には、ファイル名を解決し、エラーをログに記録するために使用できるメンバーがあります。たとえば、のようになります。

### <a name="resolve-file-names"></a>ファイル名の解決

テキストテンプレートを基準としたファイルの完全なパスを検索するには、`this.Host.ResolvePath()` を使用します。

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.IO" #>
<#
 // Find a path within the same project as the text template:
 string myFile = File.ReadAllText(this.Host.ResolvePath("MyFile.txt"));
#>
Content of myFile is:
<#= myFile #>
```

### <a name="display-error-messages"></a>エラーメッセージを表示する

この例では、テンプレートを変換するときにメッセージをログに記録します。 ホストが Visual Studio の場合は、エラーが**エラー一覧**に追加されます。

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.CodeDom.Compiler" #>
<#
  string message = "test message";
  this.Host.LogErrors(new CompilerErrorCollection()
    { new CompilerError(
       this.Host.TemplateFile, // Identify the source of the error.
       0, 0, "0",   // Line, column, error ID.
       message) }); // Message displayed in error window.
#>
```

## <a name="use-the-visual-studio-api"></a>Visual Studio API を使用する

Visual Studio でテキストテンプレートを実行している場合は、`this.Host` を使用して、Visual Studio によって提供されるサービスと読み込まれたパッケージまたは拡張機能にアクセスできます。

Hostspecific = "true" に設定し、`this.Host` を <xref:System.IServiceProvider> にキャストします。

この例では、Visual Studio API (<xref:EnvDTE.DTE>) をサービスとして取得します。

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ assembly name="EnvDTE" #>
<#@ import namespace="EnvDTE" #>
<#
 IServiceProvider serviceProvider = (IServiceProvider)this.Host;
 DTE dte = serviceProvider.GetService(typeof(DTE)) as DTE;
#>
Number of projects in this solution: <#=  dte.Solution.Projects.Count #>
```

## <a name="use-hostspecific-with-template-inheritance"></a>テンプレートの継承で hostSpecific を使用する

@No__t_1 属性も使用する場合、および `hostspecific="true"` を指定するテンプレートを継承する場合は、`hostspecific="trueFromBase"` を指定します。 そうしないと、プロパティ `Host` が2回宣言されていることを示すコンパイラの警告が表示されることがあります。