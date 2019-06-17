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
ms.openlocfilehash: 10b9091df08368674511b770158ea47c247aade7
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841368"
---
# <a name="ca3005-review-code-for-ldap-injection-vulnerabilities"></a>CA3005:LDAP インジェクションの脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForLdapInjectionVulnerabilities|
|CheckId|CA3005|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

信頼されていない可能性のある HTTP 要求の入力では、LDAP、ステートメントに到達します。

## <a name="rule-description"></a>規則の説明

信頼できない入力を使用する場合は、ライトウェイト ディレクトリ アクセス プロトコル (LDAP) インジェクション攻撃の考慮あります。 攻撃者は、情報ディレクトリに対して悪意のある LDAP ステートメントを実行することができます可能性があります。 ディレクトリ サービスにアクセスする動的な LDAP ステートメントを作成するユーザー入力を使用するアプリケーションは、特に脆弱です。

このルールは、LDAP ステートメントに到達する HTTP 要求からの入力を検索しようとします。

> [!NOTE]
> このルールは、アセンブリ間でデータを追跡することはできません。 たとえば、1 つのアセンブリが HTTP 要求の入力を読み取り、LDAP ステートメントを実行する別のアセンブリに渡されます場合は、このルールは警告を生成しません。

> [!NOTE]
> このルールがメソッド呼び出し間でデータ フローを分析する方法の詳細に構成可能な制限があります。 参照してください[アナライザーの構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)の EditorConfig ファイルで制限を構成する方法。

## <a name="how-to-fix-violations"></a>違反の修正方法

LDAP ステートメント部分ユーザー制御のいずれかを検討してください。
- 以外の特殊文字のセーフ リストのみを許可します。
- 特殊文字を許可しません。
- 特殊文字をエスケープします。

参照してください[OWASP の LDAP インジェクション防止チート シート](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/LDAP_Injection_Prevention_Cheat_Sheet.md)詳細ガイダンスについてはします。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

入力を検証または、エスケープすると、安全である場合は、この警告を抑制することができます。

## <a name="pseudo-code-examples"></a>疑似コードの例

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
