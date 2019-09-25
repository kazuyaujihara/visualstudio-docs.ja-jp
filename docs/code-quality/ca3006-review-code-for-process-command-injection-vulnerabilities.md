---
title: CA3006:プロセス コマンド インジェクションの脆弱性のコード レビュー
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
ms.openlocfilehash: 986607d7f42f49c99396bbb021c48bad549930c9
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237290"
---
# <a name="ca3006-review-code-for-process-command-injection-vulnerabilities"></a>CA3006:プロセス コマンド インジェクションの脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForProcessCommandInjectionVulnerabilities|
|CheckId|CA3006|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

信頼できない可能性のある HTTP 要求入力がプロセスコマンドに到達した場合。

## <a name="rule-description"></a>規則の説明

信頼されていない入力を使用する場合は、コマンドインジェクション攻撃に注意してください。 コマンドインジェクション攻撃は、基になるオペレーティングシステムで悪意のあるコマンドを実行し、サーバーのセキュリティと整合性を損なう可能性があります。

このルールは、プロセスコマンドに到達した HTTP 要求からの入力を検索します。

> [!NOTE]
> このルールでは、アセンブリ間のデータを追跡することはできません。 たとえば、あるアセンブリが HTTP 要求の入力を読み取ってから、プロセスを開始する別のアセンブリに渡すと、警告は生成されません。

> [!NOTE]
> このルールによって、メソッド呼び出し間のデータフローを分析する方法には、構成可能な制限があります。 EditorConfig ファイルで制限を構成する方法については、「 [Analyzer の構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)」を参照してください。

## <a name="how-to-fix-violations"></a>違反の修正方法

- 可能であれば、ユーザー入力に基づいてプロセスを開始しないようにしてください。
- 既知の安全な文字と長さのセットに対して入力を検証します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

入力が検証済みであるか、または安全であることがわかっている場合は、この警告を抑制しても安全です。

## <a name="pseudo-code-examples"></a>擬似コードの例

### <a name="violation"></a>違反

```csharp
using System;
using System.Diagnostics;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        Process p = Process.Start(input);
    }
}
```

```vb
Imports System
Imports System.Diagnostics

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs as EventArgs)
        Dim input As String = Me.Request.Form("in")
        Dim p As Process = Process.Start(input)
    End Sub
End Class
```
