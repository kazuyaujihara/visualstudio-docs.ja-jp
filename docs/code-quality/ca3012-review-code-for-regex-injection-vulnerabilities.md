---
title: CA3012:正規表現のインジェクションに対する脆弱性の確認コード
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
ms.openlocfilehash: 114b44ec566554c81f5caf3b8ac474f9c5a75c07
ms.sourcegitcommit: b6177ce198c7c5a00030604c9d4faa735405d5df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2019
ms.locfileid: "59018589"
---
# <a name="ca3012-review-code-for-regex-injection-vulnerabilities"></a>CA3012:正規表現のインジェクションに対する脆弱性の確認コード

|||
|-|-|
|TypeName|ReviewCodeForRegexInjectionVulnerabilities|
|CheckId|CA3012|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

信頼されていない可能性のある HTTP 要求の入力では、正規表現に到達します。

## <a name="rule-description"></a>規則の説明

信頼できない入力を使用する場合は、正規表現のインジェクション攻撃の考慮あります。 攻撃者は、正規表現の挿入を使用して、悪意のある、意図しない結果に一致する正規表現を作成したり、サービス拒否攻撃にその結果、過剰な CPU を消費する正規表現を作成、正規表現を変更します。

このルールは、正規表現に到達する HTTP 要求からの入力を検索しようとします。

> [!NOTE]
> このルールは、アセンブリ間でデータを追跡することはできません。 たとえば、1 つのアセンブリが HTTP 要求の入力を読み取り、正規表現を作成する別のアセンブリに渡されます場合は、このルールは警告を生成しません。

> [!NOTE]
> このルールがメソッド呼び出し間でデータ フローを分析する方法の詳細に構成可能な制限があります。 参照してください[アナライザーの構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)で制限を構成する方法の`.editorconfig`ファイル。

## <a name="how-to-fix-violations"></a>違反の修正方法

正規表現のインジェクションに対するいくつかの軽減策は次のとおりです。

- 常に使用して、[一致タイムアウト](/dotnet/standard/base-types/best-practices#use-time-out-values)正規表現を使用する場合。
- ユーザー入力に基づいて正規表現を使用しないでください。
- ユーザー入力から呼び出すことによって特殊文字をエスケープ<xref:System.Text.RegularExpressions.Regex.Escape%2A?displayProperty=fullName>または別の方法です。
- ユーザー入力からのみ特別な文字を許可します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

使用することがわかっている場合、[一致タイムアウト](/dotnet/standard/base-types/best-practices#use-time-out-values)とユーザー入力は特殊文字の無料、この警告を抑制しても問題ありません。

## <a name="pseudo-code-examples"></a>疑似コードの例

### <a name="violation"></a>違反

```csharp
using System;
using System.Text.RegularExpressions;

public partial class WebForm : System.Web.UI.Page
{
    public string SearchableText { get; set; }

    protected void Page_Load(object sender, EventArgs e)
    {
        string findTerm = Request.Form["findTerm"];
        Match m = Regex.Match(SearchableText, "^term=" + findTerm);
    }
}
```

```vb
Imports System
Imports System.Text.RegularExpressions

Public Partial Class WebForm
    Inherits System.Web.UI.Page

    Public Property SearchableText As String

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim findTerm As String = Request.Form("findTerm")
        Dim m As Match = Regex.Match(SearchableText, "^term=" + findTerm)
    End Sub
End Class
```
