---
title: CA3011:DLL インジェクションの脆弱性のコード レビュー
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
ms.openlocfilehash: a459be8c8ab028581c850f5b5770a95cb70e3510
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237191"
---
# <a name="ca3011-review-code-for-dll-injection-vulnerabilities"></a>CA3011:DLL インジェクションの脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForDllInjectionVulnerabilities|
|CheckId|CA3011|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

信頼できない可能性のある HTTP 要求入力が、アセンブリを読み込むメソッドに到達した場合。

## <a name="rule-description"></a>規則の説明

信頼できない入力を使用する場合は、信頼されていないコードを読み込むことに注意してください。 Web アプリケーションが信頼されていないコードを読み込む場合、攻撃者は悪意のある Dll をプロセスに挿入して、悪意のあるコードを実行できる可能性があります。

このルールは、アセンブリを読み込むメソッドに到達する HTTP 要求からの入力を検索します。

> [!NOTE]
> このルールでは、アセンブリ間のデータを追跡することはできません。 たとえば、あるアセンブリが HTTP 要求の入力を読み取り、アセンブリを読み込む別のアセンブリに渡すと、この規則によって警告が生成されることはありません。

> [!NOTE]
> このルールによって、メソッド呼び出し間のデータフローを分析する方法には、構成可能な制限があります。 EditorConfig ファイルで制限を構成する方法については、「 [Analyzer の構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)」を参照してください。

## <a name="how-to-fix-violations"></a>違反の修正方法

ユーザー入力から信頼されていない Dll を読み込まないでください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

このルールからの警告を抑制しないでください。

## <a name="pseudo-code-examples"></a>擬似コードの例

### <a name="violation"></a>違反

```csharp
using System;
using System.Reflection;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        byte[] rawAssembly = Convert.FromBase64String(input);
        Assembly.Load(rawAssembly);
    }
}
```

```vb
Imports System
Imports System.Reflection

Public Partial Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Request.Form("in")
        Dim rawAssembly As Byte() = Convert.FromBase64String(input)
        Assembly.Load(rawAssembly)
    End Sub
End Class
```
