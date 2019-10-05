---
title: CA3003:ファイル パス インジェクションの脆弱性のコード レビュー
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
ms.openlocfilehash: c9e43dcdf1e923cb7bc4a98b17fd0be71b7927eb
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237409"
---
# <a name="ca3003-review-code-for-file-path-injection-vulnerabilities"></a>CA3003:ファイル パス インジェクションの脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForFilePathInjectionVulnerabilities|
|CheckId|CA3003|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

信頼されていない可能性がある HTTP 要求の入力は、ファイル操作のパスに到達します。

## <a name="rule-description"></a>規則の説明

Web 要求から信頼されていない入力を使用する場合は、ファイルへのパスを指定するときにユーザーが制御する入力を使用することに注意してください。 攻撃者は意図しないファイルを読み取ることができ、その結果、機密データの情報漏えいを招く可能性があります。 または、攻撃者が意図しないファイルに書き込むことができ、その結果、機密データが不正に変更されたり、サーバーのセキュリティが侵害されたりする可能性があります。 一般的な攻撃者の手法は、目的のディレクトリの外部にあるファイルにアクセスするための[パストラバーサル](https://www.owasp.org/index.php/Path_Traversal)です。

このルールは、ファイル操作のパスに到達する HTTP 要求からの入力を検索します。

> [!NOTE]
> このルールでは、アセンブリ間のデータを追跡することはできません。 たとえば、あるアセンブリが HTTP 要求の入力を読み取り、ファイルに書き込む別のアセンブリにそのアセンブリを渡す場合、この規則は警告を生成しません。

> [!NOTE]
> このルールによって、メソッド呼び出し間のデータフローを分析する方法には、構成可能な制限があります。 EditorConfig ファイルで制限を構成する方法については、「 [Analyzer の構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)」を参照してください。

## <a name="how-to-fix-violations"></a>違反の修正方法

- 可能であれば、明示的に知られているセーフリストへのユーザー入力に基づいてファイルのパスを制限します。  たとえば、アプリケーションが "red .txt"、"green .txt"、または "blue .txt" のみにアクセスする必要がある場合は、これらの値のみを許可します。
- 信頼されていないファイル名を確認し、名前が正しい形式であることを確認します。
- パスを指定するときは、完全なパス名を使用します。
- Path 環境変数など、危険性のある構造を避けてください。
- ユーザーが短い名前を送信した場合にのみ、長いファイル名を受け入れ、長い名前を検証します。
- エンドユーザーの入力を有効な文字に制限します。
- MAX_PATH の長さを超えた場合に名前を拒否します。
- 解釈せずに、ファイル名を文字どおりに処理します。
- ファイル名がファイルまたはデバイスを表しているかどうかを確認します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

前のセクションで説明したように入力を検証した場合は、この警告を非表示にすることができます。

## <a name="pseudo-code-examples"></a>擬似コードの例

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
