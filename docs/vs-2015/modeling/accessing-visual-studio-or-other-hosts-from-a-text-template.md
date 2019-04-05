---
title: テキスト テンプレートから Visual Studio 2015 またはその他のホストへのアクセス |Microsoft Docs
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
ms.openlocfilehash: d26c168780051d3644d04d209001bf0cc9a551cb
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977478"
---
# <a name="accessing-visual-studio-or-other-hosts-from-a-text-template"></a>テキスト テンプレートから Visual Studio またはその他のホストへのアクセス
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

メソッドとなど、テンプレートを実行するホストによって公開されるプロパティを使用する、テキスト テンプレートで[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]します。

 これは、通常のテキスト テンプレート、いない前処理されたテキスト テンプレートに適用されます。

## <a name="obtaining-access-to-the-host"></a>ホストへのアクセスを取得します。
 設定`hostspecific="true"`で、`template`ディレクティブ。 使用できる`this.Host`、型を持つ<xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>します。 この型は、使用できる、たとえば、ファイル名を解決するのには、エラーをログにメンバーがあります。

### <a name="resolving-file-names"></a>ファイル名を解決します。
 テキスト テンプレートに関連するファイルの完全なパスを検索するには、これを使用します。Host.ResolvePath() します。

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

### <a name="displaying-error-messages"></a>エラー メッセージを表示します。
 この例は、テンプレートを変換するときのメッセージを記録します。 ホストが場合[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]、エラー ウィンドウに追加されます。

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

## <a name="using-the-visual-studio-api"></a>Visual Studio API を使用
 テキスト テンプレートを実行している場合[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]、使用することができます`this.Host`によって提供されるサービスへのアクセス[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]とパッケージまたは読み込まれている拡張機能。

 `hostspecific ="true"` を設定し、`this.Host` を <xref:System.IServiceProvider> にキャストします。

 この例の取得、 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] API、 <xref:EnvDTE.DTE>、サービスとして。

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

## <a name="using-hostspecific-with-template-inheritance"></a>テンプレートの継承を持つ hostSpecific を使用します。
 `inherits`属性を使用し、`hostspecific="true"` を指定したテンプレートから継承する場合は、`hostspecific="trueFromBase"` を指定します。 効果にコンパイラの警告を回避できるプロパティ`Host`は 2 回宣言されています。
