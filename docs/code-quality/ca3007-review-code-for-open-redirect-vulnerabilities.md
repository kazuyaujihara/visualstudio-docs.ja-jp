---
title: CA3007:オープン リダイレクトの脆弱性のコード レビュー
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
ms.openlocfilehash: dbafb6c05a3dba72d1614d6a955e20030a50c6ea
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541169"
---
# <a name="ca3007-review-code-for-open-redirect-vulnerabilities"></a>CA3007:オープン リダイレクトの脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForOpenRedirectVulnerabilities|
|CheckId|CA3007|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

信頼されていない可能性のある HTTP 要求の入力では、HTTP 応答のリダイレクトに到達します。

## <a name="rule-description"></a>規則の説明

信頼できない入力を使用する場合は、オープン リダイレクト脆弱性の考慮あります。 攻撃者は、web サイトを使用して、正当な URL の外観を与えるが、フィッシングやその他の悪意のある web ページを戸惑わせるビジターをリダイレクトする、オープン リダイレクト脆弱性を利用できます。

このルールは、HTTP のリダイレクト URL に到達する HTTP 要求からの入力を検索しようとします。

> [!NOTE]
> このルールは、アセンブリ間でデータを追跡することはできません。 などの場合は 1 つのアセンブリでは、HTTP 要求の入力を読み取りし、別のアセンブリは、HTTP リダイレクトで応答に渡されますが、このルールは警告を生成しません。

> [!NOTE]
> このルールがメソッド呼び出し間でデータ フローを分析する方法の詳細に構成可能な制限があります。 参照してください[アナライザーの構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)で制限を構成する方法の`.editorconfig`ファイル。

## <a name="how-to-fix-violations"></a>違反の修正方法

オープン リダイレクト脆弱性を修正するいくつかの方法は次のとおりです。

- リダイレクトを開始するユーザーを禁止します。
- リダイレクトのシナリオでは、URL の一部を指定するユーザーを禁止します。
- ように、定義済み"リスト"Url のリダイレクトを制限します。
- 検証 Url をリダイレクトします。
- 該当する場合は、免責事項ページを使用して、ユーザーが、サイトから離れた場所にリダイレクトされるときに検討してください。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

目的の Url に制限するへの入力を検証した場合は、この警告を抑制することができます。

## <a name="pseudo-code-examples"></a>疑似コードの例

### <a name="violation"></a>違反

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["url"];
        this.Response.Redirect(input);
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Dim input As String = Me.Request.Form("url")
        Me.Response.Redirect(input)
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
        if (String.IsNullOrWhiteSpace(input))
        {
            this.Response.Redirect("https://example.org/login.html");
        }
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Dim input As String = Me.Request.Form("in")
        If String.IsNullOrWhiteSpace(input) Then
            Me.Response.Redirect("https://example.org/login.html")
        End If
    End Sub
End Class
```
