---
title: CA3003:コード ファイルのパスのインジェクションに対する脆弱性を確認します。
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
ms.openlocfilehash: c20d3efb9ea84a7e8bb22288303313ef44b2b795
ms.sourcegitcommit: b6177ce198c7c5a00030604c9d4faa735405d5df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2019
ms.locfileid: "59018597"
---
# <a name="ca3003-review-code-for-file-path-injection-vulnerabilities"></a>CA3003:コード ファイルのパスのインジェクションに対する脆弱性を確認します。

|||
|-|-|
|TypeName|ReviewCodeForFilePathInjectionVulnerabilities|
|CheckId|CA3003|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

信頼されていない可能性のある HTTP 要求の入力では、ファイル操作のパスに到達します。

## <a name="rule-description"></a>規則の説明

Web 要求から信頼されていない入力を使用する場合は、ユーザーに制御された入力を使用してファイルへのパスを指定するときに考慮あります。 攻撃者は機密データの情報漏えいが起こるは入力が、意図しないファイルを読み取ることができます。 または、機密データの不正な変更結果として、またはサーバーのセキュリティを損なうことに、攻撃者が、意図しないファイルへの書き込みすることができます。 一般的な攻撃者の手法は[パス トラバーサル](https://www.owasp.org/index.php/Path_Traversal)目的のディレクトリの外部ファイルにアクセスします。

このルールは、ファイルの操作でのパスに到達する HTTP 要求からの入力を検索しようとします。

> [!NOTE]
> このルールは、アセンブリ間でデータを追跡することはできません。 たとえば場合、1 つのアセンブリでは、HTTP 要求の入力を読み取ってファイルへの書き込みを別のアセンブリに渡されます、このルールは警告を生成しません。

> [!NOTE]
> このルールがメソッド呼び出し間でデータ フローを分析する方法の詳細に構成可能な制限があります。 参照してください[アナライザーの構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)で制限を構成する方法の`.editorconfig`ファイル。

## <a name="how-to-fix-violations"></a>違反の修正方法

- 可能であれば、ファイル パスを明示的に既知のセーフ リストにユーザー入力に基づいたを制限します。  たとえば、アプリケーションは、"red.txt"、"green.txt"または"blue.txt"アクセスのみが場合はのみ、これらの値を許可します。
- 信頼されていないファイル名を確認し、名前が整形式でことを検証します。
- パスを指定する場合は、完全なパス名を使用します。
- Path 環境変数などの危険性のある構造を回避します。
- のみの長いファイル名をそのまま使用し、ユーザーは、短い名前を送信する場合は、長い名前を検証します。
- 有効な文字へのエンド ユーザー入力を制限します。
- 長さの MAX_PATH を超える名前を拒否します。
- 文字どおり、解釈なしのファイル名を処理します。
- ファイルまたはデバイスにファイル名を表すかどうかを決定します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

場合は、前のセクションで説明されているように入力を検証した、この警告を抑制することができます。

## <a name="pseudo-code-examples"></a>疑似コードの例

### <a name="violation"></a>違反

```csharp
using System;
using System.IO;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string userInput = Request.Params["UserInput"];
        // Assume the following directory structure:
        //   wwwroot\currentWebDirectory\user1.txt
        //   wwwroot\currentWebDirectory\user2.txt
        //   wwwroot\secret\allsecrets.txt
        // There is nothing wrong if the user inputs:
        //   user1.txt
        // However, if the user input is: 
        //   ..\secret\allsecrets.txt
        // Then an attacker can now see all the secrets.

        // Avoid this:
        using (File.Open(userInput, FileMode.Open))
        {
            // Read a file with the name supplied by user
            // Input through request's query string and display 
            // The content to the webpage. 
        }
    }
}
```

```vb
Imports System
Imports System.IO

Partial Public Class WebForm 
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim userInput As String = Me.Request.Params("UserInput")
        ' Assume the following directory structure:
        '   wwwroot\currentWebDirectory\user1.txt
        '   wwwroot\currentWebDirectory\user2.txt
        '   wwwroot\secret\allsecrets.txt
        ' There is nothing wrong if the user inputs:
        '   user1.txt
        ' However, if the user input is: 
        '   ..\secret\allsecrets.txt
        ' Then an attacker can now see all the secrets.

        ' Avoid this:
        Using File.Open(userInput, FileMode.Open)
            ' Read a file with the name supplied by user
            ' Input through request's query string and display 
            ' The content to the webpage. 
        End Using
    End Sub
End Class
```
