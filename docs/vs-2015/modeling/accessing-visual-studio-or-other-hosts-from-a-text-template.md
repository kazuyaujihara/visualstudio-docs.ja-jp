---
title: テキストテンプレートから Visual Studio 2015 またはその他のホストにアクセスする |Microsoft Docs
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: a68886da-7416-4785-8145-3796bb382cba
caps.latest.revision: 7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0e8cedc66d6b52f80239364a3e51b73e93a69aa4
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72655332"
---
# <a name="accessing-visual-studio-or-other-hosts-from-a-text-template"></a>テキスト テンプレートから Visual Studio またはその他のホストへのアクセス
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

テキストテンプレートでは、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] など、テンプレートを実行するホストによって公開されているメソッドとプロパティを使用できます。

 これは、プリプロセスされたテキストテンプレートではなく、通常のテキストテンプレートに適用されます。

## <a name="obtaining-access-to-the-host"></a>ホストへのアクセスを取得しています

@No__t_1 ディレクティブで `hostspecific="true"` を設定します。 これにより、 [ITextTemplatingEngineHost](/previous-versions/visualstudio/visual-studio-2012/bb126505(v=vs.110))型の `this.Host` を使用できます。 この型には、ファイル名を解決したりエラーをログに記録したりするために使用できるメンバーが含まれています。

### <a name="resolving-file-names"></a>ファイル名の解決
 テキストテンプレートを基準としたファイルの完全なパスを検索するには、これを使用します。ホストの ResolvePath ()。

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

### <a name="displaying-error-messages"></a>エラーメッセージの表示
 この例では、テンプレートを変換するときにメッセージをログに記録します。 ホストが [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 場合は、エラーウィンドウに追加されます。

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

## <a name="using-the-visual-studio-api"></a>Visual Studio API の使用
 @No__t_0 でテキストテンプレートを実行している場合は、`this.Host` を使用して、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] によって提供されるサービスと読み込まれたパッケージまたは拡張機能にアクセスできます。

 Hostspecific = "true" に設定し、`this.Host` を <xref:System.IServiceProvider> にキャストします。

 この例では、サービスとして [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] API、<xref:EnvDTE.DTE> を取得します。

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

## <a name="using-hostspecific-with-template-inheritance"></a>テンプレート継承での hostSpecific の使用
 @No__t_1 属性も使用する場合、および `hostspecific="true"` を指定するテンプレートを継承する場合は、`hostspecific="trueFromBase"` を指定します。 これにより、プロパティ `Host` が2回宣言されているという結果に対するコンパイラ警告が回避されます。
