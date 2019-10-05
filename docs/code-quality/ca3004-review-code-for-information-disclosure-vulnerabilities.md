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
ms.openlocfilehash: 4965c9df3c2256511b8e44de8d388a9155d0d8f9
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237374"
---
# <a name="ca3004-review-code-for-information-disclosure-vulnerabilities"></a>CA3004:情報漏えいの脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForInformationDisclosureVulnerabilities|
|CheckId|CA3004|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

例外のメッセージ、スタックトレース、または文字列表現が web 出力に到達します。

## <a name="rule-description"></a>規則の説明

例外情報を公開すると、攻撃者がアプリケーションの内部を調べて、攻撃者が他の脆弱性を悪用するのを支援することができます。

このルールは、HTTP 応答に出力されている例外メッセージ、スタックトレース、または文字列表現の検索を試みます。

> [!NOTE]
> このルールでは、アセンブリ間のデータを追跡することはできません。 たとえば、あるアセンブリが例外をキャッチし、例外を出力する別のアセンブリにそのアセンブリを渡すと、この規則によって警告が生成されることはありません。

> [!NOTE]
> このルールによって、メソッド呼び出し間のデータフローを分析する方法には、構成可能な制限があります。 EditorConfig ファイルで制限を構成する方法については、「 [Analyzer の構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)」を参照してください。

## <a name="how-to-fix-violations"></a>違反の修正方法

例外情報を HTTP 応答に出力しません。 代わりに、一般的なエラーメッセージを指定してください。 詳細については、 [Owasp のエラー処理](https://www.owasp.org/index.php/Error_Handling)に関するページを参照してください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

Web 出力がアプリケーションの信頼境界内にあり、外部に公開されていないことがわかっている場合は、この警告を非表示にすることができます。 これはめったにありません。 アプリケーションの信頼境界とデータフローが時間の経過と共に変わる可能性があることを考慮してください。

## <a name="pseudo-code-examples"></a>擬似コードの例

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