---
title: テキストテンプレートから Visual Studio 2015 またはその他のホストにアクセスする |Microsoft Docs
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: a68886da-7416-4785-8145-3796bb382cba
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 053e8b09fd2b52683238f1ffe008e5e7d38b3962
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68872006"
---
# <a name="accessing-visual-studio-or-other-hosts-from-a-text-template"></a>テキスト テンプレートから Visual Studio またはその他のホストへのアクセス
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

テキストテンプレートでは、など、テンプレート[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]を実行するホストによって公開されているメソッドとプロパティを使用できます。

 これは、プリプロセスされたテキストテンプレートではなく、通常のテキストテンプレートに適用されます。

## <a name="obtaining-access-to-the-host"></a>ホストへのアクセスを取得しています

ディレクティブでを設定`hostspecific="true"`します。 `template` これにより、 `this.Host` [ITextTemplatingEngineHost](/previous-versions/visualstudio/visual-studio-2012/bb126505(v=vs.110))型のを使用できます。 この型には、ファイル名を解決したりエラーをログに記録したりするために使用できるメンバーが含まれています。

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
 この例は、テンプレートを変換するときのメッセージを記録します。 ホストが[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]の場合は、エラーウィンドウに追加されます。

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
 で[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]テキストテンプレートを実行している場合は、を`this.Host`使用して、に[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]よって提供されるサービスと読み込まれたパッケージまたは拡張機能にアクセスできます。

 `hostspecific ="true"` を設定し、`this.Host` を <xref:System.IServiceProvider> にキャストします。

 この例では[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 、API <xref:EnvDTE.DTE>をサービスとして取得します。

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
 `inherits`属性を使用し、`hostspecific="true"` を指定したテンプレートから継承する場合は、`hostspecific="trueFromBase"` を指定します。 これにより、プロパティ`Host`が2回宣言されているという結果に対するコンパイラ警告が回避されます。
