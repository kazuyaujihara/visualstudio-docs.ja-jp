---
title: CA3012:RegEx インジェクションの脆弱性のコード レビュー
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
ms.openlocfilehash: 42808b3961b18a23f594800f9d0782c908c9b1ba
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237186"
---
# <a name="ca3012-review-code-for-regex-injection-vulnerabilities"></a>CA3012:RegEx インジェクションの脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForRegexInjectionVulnerabilities|
|CheckId|CA3012|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

信頼できない可能性のある HTTP 要求入力が正規表現に到達した場合。

## <a name="rule-description"></a>規則の説明

信頼できない入力を使用する場合は、regex インジェクション攻撃に注意してください。 攻撃者は、regex インジェクションを使用して正規表現を故意に変更したり、regex が意図しない結果に一致するようにしたり、regex が過剰な CPU を消費してサービス拒否攻撃を受ける可能性があります。

このルールは、正規表現に到達する HTTP 要求からの入力を検索します。

> [!NOTE]
> このルールでは、アセンブリ間のデータを追跡することはできません。 たとえば、あるアセンブリが HTTP 要求入力を読み取り、それを正規表現を作成する別のアセンブリに渡す場合、この規則は警告を生成しません。

> [!NOTE]
> このルールによって、メソッド呼び出し間のデータフローを分析する方法には、構成可能な制限があります。 EditorConfig ファイルで制限を構成する方法については、「 [Analyzer の構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)」を参照してください。

## <a name="how-to-fix-violations"></a>違反の修正方法

Regex インジェクションに対する軽減策は次のとおりです。

- 正規表現を使用する場合は、常に[一致のタイムアウト](/dotnet/standard/base-types/best-practices#use-time-out-values)を使用します。
- ユーザー入力に基づいて正規表現を使用することは避けてください。
- または別のメソッドを呼び出す<xref:System.Text.RegularExpressions.Regex.Escape%2A?displayProperty=fullName>ことによって、ユーザー入力から特殊文字をエスケープします。
- ユーザー入力からの特殊文字以外の文字のみを許可します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

[一致のタイムアウト](/dotnet/standard/base-types/best-practices#use-time-out-values)を使用していることがわかっていて、ユーザー入力が特殊文字を使用していないことがわかっている場合は、この警告を非表示にすることができます。

## <a name="pseudo-code-examples"></a>擬似コードの例

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
