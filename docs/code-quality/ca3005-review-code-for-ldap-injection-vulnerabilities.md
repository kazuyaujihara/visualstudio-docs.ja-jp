---
title: CA3005:LDAP インジェクションの脆弱性のコード レビュー
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
ms.openlocfilehash: c0c99d5d0adb145a061693f8a83b1f674e05eed4
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237342"
---
# <a name="ca3005-review-code-for-ldap-injection-vulnerabilities"></a>CA3005:LDAP インジェクションの脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForLdapInjectionVulnerabilities|
|CheckId|CA3005|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

信頼できない可能性のある HTTP 要求入力が LDAP ステートメントに到達した場合。

## <a name="rule-description"></a>規則の説明

信頼されていない入力を使用する場合は、ライトウェイトディレクトリアクセスプロトコル (LDAP) インジェクション攻撃に注意してください。 攻撃者は、情報ディレクトリに対して悪意のある LDAP ステートメントを実行する可能性があります。 ユーザー入力を使用してディレクトリサービスにアクセスするための動的 LDAP ステートメントを作成するアプリケーションは、特に脆弱です。

このルールは、LDAP ステートメントに到達した HTTP 要求からの入力を検索します。

> [!NOTE]
> このルールでは、アセンブリ間のデータを追跡することはできません。 たとえば、あるアセンブリが HTTP 要求の入力を読み取り、それを LDAP ステートメントを実行する別のアセンブリに渡す場合、この規則は警告を生成しません。

> [!NOTE]
> このルールによって、メソッド呼び出し間のデータフローを分析する方法には、構成可能な制限があります。 EditorConfig ファイルで制限を構成する方法については、「 [Analyzer の構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)」を参照してください。

## <a name="how-to-fix-violations"></a>違反の修正方法

LDAP ステートメントのユーザー制御部分については、次のいずれかを検討してください。
- 特殊文字以外の文字のセーフリストのみを許可します。
- 特殊文字を許可しない
- 特殊文字をエスケープします。

詳細については、 [Owasp の LDAP インジェクション防止](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/LDAP_Injection_Prevention_Cheat_Sheet.md)に関する表を参照してください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

入力が検証済みであるか、または安全であることがわかっている場合は、この警告を非表示にすることができます。

## <a name="pseudo-code-examples"></a>擬似コードの例

### <a name="violation"></a>違反

```csharp
using System;
using System.DirectoryServices;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string userName = Request.Params["user"];
        string filter = "(uid=" + userName + ")";  // searching for the user entry

        // In this example, if we send the * character in the user parameter which will
        // result in the filter variable in the code to be initialized with (uid=*).
        // The resulting LDAP statement will make the server return any object that
        // contains a uid attribute.
        DirectorySearcher searcher = new DirectorySearcher(filter);
        SearchResultCollection results = searcher.FindAll();

        // Iterate through each SearchResult in the SearchResultCollection.
        foreach (SearchResult searchResult in results)
        {
            // ...
        }
    }
}
```

```vb
Imports System
Imports System.DirectoryServices

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(send As Object, e As EventArgs)
        Dim userName As String = Me.Request.Params(""user"")
        Dim filter As String = ""(uid="" + userName + "")""    ' searching for the user entry

        ' In this example, if we send the * character in the user parameter which will
        ' result in the filter variable in the code to be initialized with (uid=*).
        ' The resulting LDAP statement will make the server return any object that
        ' contains a uid attribute.
        Dim searcher As DirectorySearcher = new DirectorySearcher(filter)
        Dim results As SearchResultCollection = searcher.FindAll()

        ' Iterate through each SearchResult in the SearchResultCollection.
        For Each searchResult As SearchResult in results
            ' ...
        Next searchResult
    End Sub
End Class
```
