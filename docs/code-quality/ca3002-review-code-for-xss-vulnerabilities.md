---
title: CA3002:XSS の脆弱性のコード レビュー
ms.date: 04/03/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 6bcf32401abdeae499097bc5187d11154e7dfc6e
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237418"
---
# <a name="ca3002-review-code-for-xss-vulnerabilities"></a>CA3002:XSS の脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForXssVulnerabilities|
|CheckId|CA3002|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

信頼できない可能性のある HTTP 要求入力が、未加工の HTML 出力になります。

## <a name="rule-description"></a>規則の説明

Web 要求から信頼されていない入力を処理する場合は、クロスサイトスクリプティング (XSS) 攻撃に注意する必要があります。 XSS 攻撃によって、信頼できない入力が未加工の HTML 出力に挿入され、攻撃者が悪意のあるスクリプトを実行したり、web ページのコンテンツを改ざんしたりする可能性があります。 一般的な手法では`<script>` 、要素を入力に悪意のあるコードと共に配置します。 詳細については、「 [Owasp の XSS](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS))」を参照してください。

このルールは、未加工の HTML 出力に到達する HTTP 要求からの入力を検索します。

> [!NOTE]
> このルールでは、アセンブリ間のデータを追跡することはできません。 たとえば、あるアセンブリが HTTP 要求の入力を読み取り、生の HTML を出力する別のアセンブリにそのアセンブリを渡す場合、この規則は警告を生成しません。

> [!NOTE]
> このルールによって、メソッド呼び出し間のデータフローを分析する方法には、構成可能な制限があります。 EditorConfig ファイルで制限を構成する方法については、「 [Analyzer の構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)」を参照してください。

## <a name="how-to-fix-violations"></a>違反の修正方法

- 生の HTML を出力するのではなく、最初に入力を HTML エンコードするメソッドまたはプロパティを使用します。
- 生の HTML を出力する前に、信頼されていないデータを HTML エンコードします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

次の場合は、この規則による警告を抑制しても安全です。
- 入力は、HTML を含まない既知の安全な文字セットに対して検証されていることがわかります。
- この規則で検出されない方法でデータが HTML エンコードされていることがわかっています。

> [!NOTE]
> このルールは、入力を HTML エンコードするメソッドまたはプロパティについて、偽陽性を報告する場合があります。

## <a name="pseudo-code-examples"></a>擬似コードの例

### <a name="violation"></a>違反

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        Response.Write("<HTML>" + input + "</HTML>");
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Me.Request.Form("in")
        Me.Response.Write("<HTML>" + input + "</HTML>")
    End Sub
End Class
```

### <a name="solution"></a>ソリューション

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];

        // Example usage of System.Web.HttpServerUtility.HtmlEncode().
        Response.Write("<HTML>" + Server.HtmlEncode(input) + "</HTML>");
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Me.Request.Form("in")

        ' Example usage of System.Web.HttpServerUtility.HtmlEncode().
        Me.Response.Write("<HTML>" + Me.Server.HtmlEncode(input) + "</HTML>")
    End Sub
End Class
```