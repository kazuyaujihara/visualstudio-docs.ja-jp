---
title: CA3004:情報漏えいの脆弱性のコード レビュー
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
ms.openlocfilehash: 8e8c8c58a01b9527df472907c8b55a9d175dd91d
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841611"
---
# <a name="ca3004-review-code-for-information-disclosure-vulnerabilities"></a>CA3004:情報漏えいの脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForInformationDisclosureVulnerabilities|
|CheckId|CA3004|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

例外のメッセージ、スタック トレース、または文字列形式には、web の出力に到達します。

## <a name="rule-description"></a>規則の説明

攻撃者が攻撃者に役立つ、アプリケーションの内部構造に関する洞察を悪用するその他の脆弱性の検索は、例外情報の開示。

このルールは、例外メッセージ、スタック トレース、または HTTP 応答に出力される文字列形式を検索しようとします。

> [!NOTE]
> このルールは、アセンブリ間でデータを追跡することはできません。 たとえば場合、1 つのアセンブリは、例外をキャッチし、例外を出力する別のアセンブリに渡されます、このルールは警告を生成しません。

> [!NOTE]
> このルールがメソッド呼び出し間でデータ フローを分析する方法の詳細に構成可能な制限があります。 参照してください[アナライザーの構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)の EditorConfig ファイルで制限を構成する方法。

## <a name="how-to-fix-violations"></a>違反の修正方法

例外情報を HTTP 応答の出力はありません。 代わりに、一般的なエラー メッセージを提供します。 参照してください[OWASP のエラー処理ページ](https://www.owasp.org/index.php/Error_Handling)詳細ガイダンスについてはします。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

わかっている場合、web の出力は、アプリケーションの信頼境界内でありの外部に公開しない、ではこの警告を抑制します。 これはまれです。 アプリケーションの信頼境界とデータ フローは、時間の経過と共に変わる可能性のある考慮に入れてください。

## <a name="pseudo-code-examples"></a>疑似コードの例

### <a name="violation"></a>違反

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs eventArgs)
    {
        try
        {
            object o = null;
            o.ToString();
        }
        catch (Exception e)
        {
            this.Response.Write(e.ToString());
        }
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Try
            Dim o As Object = Nothing
            o.ToString()
        Catch e As Exception
            Me.Response.Write(e.ToString())
        End Try
    End Sub
End Class
```

### <a name="solution"></a>ソリューション

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs eventArgs)
    {
        try
        {
            object o = null;
            o.ToString();
        }
        catch (Exception e)
        {
            this.Response.Write("An error occurred. Please try again later.");
        }
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Try
            Dim o As Object = Nothing
            o.ToString()
        Catch e As Exception
            Me.Response.Write("An error occurred. Please try again later.")
        End Try
    End Sub
End Class
```