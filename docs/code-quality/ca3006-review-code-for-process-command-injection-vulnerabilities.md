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
ms.openlocfilehash: da161e611ca1d802c8da16370907029233bfd785
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60037986"
---
# <a name="ca3006-review-code-for-process-command-injection-vulnerabilities"></a>CA3006:プロセス コマンド インジェクションの脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForProcessCommandInjectionVulnerabilities|
|CheckId|CA3006|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

信頼されていない可能性のある HTTP 要求の入力では、プロセス コマンドに到達します。

## <a name="rule-description"></a>規則の説明

信頼できない入力を使用する場合は、コマンド インジェクション攻撃の考慮あります。 コマンドのインジェクション攻撃は、基になるオペレーティング システム、セキュリティと、サーバーの整合性を損なうことに、悪意のあるコマンドを実行できます。

このルールは、プロセス コマンドに到達する HTTP 要求からの入力を検索しようとします。

> [!NOTE]
> このルールは、アセンブリ間でデータを追跡することはできません。 たとえば場合、1 つのアセンブリは、HTTP 要求の入力を読み取って、プロセスを開始する別のアセンブリに渡されます、このルールは警告を生成しません。

> [!NOTE]
> このルールがメソッド呼び出し間でデータ フローを分析する方法の詳細に構成可能な制限があります。 参照してください[アナライザーの構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)で制限を構成する方法の`.editorconfig`ファイル。

## <a name="how-to-fix-violations"></a>違反の修正方法

- 可能であれば、ユーザー入力に基づいてプロセスを開始しないでください。
- 既知の安全な文字と長さのセットに対する入力を検証します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

入力を検証または、安全のためのエスケープがわかっている場合は、この警告を抑制しても安全です。

## <a name="pseudo-code-examples"></a>疑似コードの例

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
