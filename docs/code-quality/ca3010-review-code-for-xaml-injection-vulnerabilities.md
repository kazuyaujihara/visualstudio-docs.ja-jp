---
title: CA3010:XAML インジェクションの脆弱性のコード レビュー
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
ms.openlocfilehash: 965e0d800bd7c725236d96499d2bf2d441b40412
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841090"
---
# <a name="ca3010-review-code-for-xaml-injection-vulnerabilities"></a>CA3010:XAML インジェクションの脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForXamlInjectionVulnerabilities|
|CheckId|CA3010|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

信頼されていない可能性のある HTTP 要求の入力に達すると、 <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> Load メソッド。

## <a name="rule-description"></a>規則の説明

信頼できない入力を使用する場合は、XAML のインジェクション攻撃の考慮あります。 XAML は、オブジェクトのインスタンス化と実行を直接表すマークアップ言語です。 つまり、XAML で作成された要素は、システム リソース (たとえば、ネットワーク アクセスとファイル システム IO) とやり取りできます。 攻撃者への入力を制御できる場合、<xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType>攻撃者がコードを実行し、メソッドの呼び出しをロードします。

このルールに到達する HTTP 要求からの入力を検出しようとしています、 <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> Load メソッド。

> [!NOTE]
> このルールは、アセンブリ間でデータを追跡することはできません。 たとえば、1 つのアセンブリが HTTP 要求の入力を読み取り、別のアセンブリを XAML に渡されます場合は、このルールは警告を生成しません。

> [!NOTE]
> このルールがメソッド呼び出し間でデータ フローを分析する方法の詳細に構成可能な制限があります。 参照してください[アナライザーの構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)の EditorConfig ファイルで制限を構成する方法。

## <a name="how-to-fix-violations"></a>違反の修正方法

信頼されていない XAML をロードしません。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告を抑制はありません。

## <a name="pseudo-code-examples"></a>疑似コードの例

### <a name="violation"></a>違反

```csharp
using System;
using System.IO;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        byte[] bytes = Convert.FromBase64String(input);
        MemoryStream ms = new MemoryStream(bytes);
        System.Windows.Markup.XamlReader.Load(ms);
    }
}
```

```vb
Imports System
Imports System.IO

Public Partial Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Request.Form("in")
        Dim bytes As Byte() = Convert.FromBase64String(input)
        Dim ms As MemoryStream = New MemoryStream(bytes)
        System.Windows.Markup.XamlReader.Load(ms)
    End Sub
End Class
```
