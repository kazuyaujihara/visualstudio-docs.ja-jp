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
ms.openlocfilehash: a10f72297746a1e7bda3c69f8f7daf0efacd20bc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541268"
---
# <a name="ca3002-review-code-for-xss-vulnerabilities"></a>CA3002:XSS の脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForXssVulnerabilities|
|CheckId|CA3002|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

信頼されていない可能性のある HTTP 要求の入力では、生の HTML 出力に到達します。

## <a name="rule-description"></a>規則の説明

Web 要求から信頼されていない入力を使用する場合はあるクロスサイト スクリプティング (XSS) 攻撃に注意してください。 XSS 攻撃は、攻撃者が悪意のあるスクリプトの実行や、悪意のある web ページのコンテンツを変更できる生の HTML 出力に、信頼できない入力を挿入します。 一般的な手法を配置する`<script>`入力で悪意のあるコードを持つ要素。 詳細については、次を参照してください。 [OWASP の XSS](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS))します。

このルールは、生の HTML 出力に到達する HTTP 要求からの入力を検索しようとします。

> [!NOTE]
> このルールは、アセンブリ間でデータを追跡することはできません。 たとえば場合は、1 つのアセンブリは、HTTP 要求の入力を読み取って、生の HTML を出力する別のアセンブリに渡されます、このルールは警告を生成しません。

> [!NOTE]
> このルールがメソッド呼び出し間でデータ フローを分析する方法の詳細に構成可能な制限があります。 参照してください[アナライザーの構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)で制限を構成する方法の`.editorconfig`ファイル。

## <a name="how-to-fix-violations"></a>違反の修正方法

- 生の HTML を出力するには、代わりにそのその最初を HTML エンコードの入力メソッドまたはプロパティを使用します。
- HTML エンコードでは、生の HTML を出力する前にデータを信頼されていません。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

場合、この規則による警告を抑制しても安全です。
- 既知の安全な HTML が含まれていない文字のセットに対して、入力を検証することがわかります。
- このルールで検出されない方法で HTML でエンコードされたデータがわかります。

> [!NOTE]
> この規則は偽陽性のいくつかのメソッドまたはプロパティをレポートがその HTML エンコードが入力されます。

## <a name="pseudo-code-examples"></a>疑似コードの例

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