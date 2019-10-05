---
title: CA3001:SQL インジェクションの脆弱性のコード レビュー
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
ms.openlocfilehash: bd454ffad1efc9d7df84d88630fe71eebc8ca6fc
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71238117"
---
# <a name="ca3001-review-code-for-sql-injection-vulnerabilities"></a>CA3001:SQL インジェクションの脆弱性のコード レビュー

|||
|-|-|
|TypeName|ReviewCodeForSqlInjectionsVulnerabilities|
|CheckId|CA3001|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

信頼できない可能性のある HTTP 要求入力が SQL コマンドのテキストに到達した場合。

## <a name="rule-description"></a>規則の説明

信頼されていない入力と SQL コマンドを使用する場合は、SQL インジェクション攻撃に注意してください。 SQL インジェクション攻撃によって、悪意のある SQL コマンドを実行し、アプリケーションのセキュリティと整合性を損なう可能性があります。 一般的な手法としては、リテラル文字列の区切りに単一引用符またはアポストロフィを使用したり、コメントに2つのダッシュを使用したり、ステートメントの最後にセミコロンを使用したりする方法があります。 詳細については、「 [SQL インジェクション](/sql/relational-databases/security/sql-injection)」を参照してください。

このルールは、SQL コマンドのテキストに到達する HTTP 要求からの入力を検索します。

> [!NOTE]
> このルールでは、アセンブリ間のデータを追跡することはできません。 たとえば、あるアセンブリが HTTP 要求の入力を読み取り、それを SQL コマンドを実行する別のアセンブリに渡す場合、この規則は警告を生成しません。

> [!NOTE]
> このルールによって、メソッド呼び出し間のデータフローを分析する方法には、構成可能な制限があります。 EditorConfig ファイルで制限を構成する方法については、「 [Analyzer の構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis)」を参照してください。

## <a name="how-to-fix-violations"></a>違反の修正方法

パラメーター化された SQL コマンドまたはストアドプロシージャを、信頼できない入力を含むパラメーターと共に使用します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

入力が既知の安全な文字セットに対して常に検証されることがわかっている場合は、この規則による警告を抑制しても安全です。

## <a name="pseudo-code-examples"></a>擬似コードの例

### <a name="violation"></a>違反

```csharp
using System;
using System.Data;
using System.Data.SqlClient;

namespace TestNamespace
{
    public partial class WebForm : System.Web.UI.Page
    {
        public static string ConnectionString { get; set; }

        protected void Page_Load(object sender, EventArgs e)
        {
            string name = Request.Form["product_name"];
            using (SqlConnection connection = new SqlConnection(ConnectionString))
            {
                SqlCommand sqlCommand = new SqlCommand()
                {
                    CommandText = "SELECT ProductId FROM Products WHERE ProductName = '" + name + "'",
                    CommandType = CommandType.Text,
                };

                SqlDataReader reader = sqlCommand.ExecuteReader();
            }
        }
    }
}
```

```vb
Imports System
Imports System.Data
Imports System.Data.SqlClient
Imports System.Linq

Namespace VulnerableWebApp
    Partial Public Class WebForm
        Inherits System.Web.UI.Page

        Public Property ConnectionString As String

        Protected Sub Page_Load(sender As Object, e As EventArgs)
            Dim name As String = Me.Request.Form("product_name")
            Using connection As SqlConnection = New SqlConnection(ConnectionString)
                Dim sqlCommand As SqlCommand = New SqlCommand With {.CommandText = "SELECT ProductId FROM Products WHERE ProductName = '" + name + "'",
                                                                    .CommandType = CommandType.Text}
                Dim reader As SqlDataReader = sqlCommand.ExecuteReader()
            End Using
        End Sub
    End Class
End Namespace
```

### <a name="parameterized-solution"></a>パラメーター化されたソリューション

```csharp
using System;
using System.Data;
using System.Data.SqlClient;

namespace TestNamespace
{
    public partial class WebForm : System.Web.UI.Page
    {
        public static string ConnectionString { get; set; }

        protected void Page_Load(object sender, EventArgs e)
        {
            string name = Request.Form["product_name"];
            using (SqlConnection connection = new SqlConnection(ConnectionString))
            {
                SqlCommand sqlCommand = new SqlCommand()
                {
                    CommandText = "SELECT ProductId FROM Products WHERE ProductName = @productName",
                    CommandType = CommandType.Text,
                };

                sqlCommand.Parameters.Add("@productName", SqlDbType.NVarChar, 128).Value = name;

                SqlDataReader reader = sqlCommand.ExecuteReader();
            }
        }
    }
}
```

```vb
Imports System
Imports System.Data
Imports System.Data.SqlClient
Imports System.Linq

Namespace VulnerableWebApp
    Partial Public Class WebForm
        Inherits System.Web.UI.Page

        Public Property ConnectionString As String

        Protected Sub Page_Load(sender As Object, e As EventArgs)
            Dim name As String = Me.Request.Form("product_name")
            Using connection As SqlConnection = New SqlConnection(ConnectionString)
                Dim sqlCommand As SqlCommand = New SqlCommand With {.CommandText = "SELECT ProductId FROM Products WHERE ProductName = @productName",
                                                                    .CommandType = CommandType.Text}
                sqlCommand.Parameters.Add("@productName", SqlDbType.NVarChar, 128).Value = name
                Dim reader As SqlDataReader = sqlCommand.ExecuteReader()
            End Using
        End Sub
    End Class
End Namespace
```

### <a name="stored-procedure-solution"></a>ストアドプロシージャソリューション

```csharp
using System;
using System.Data;
using System.Data.SqlClient;

namespace TestNamespace
{
    public partial class WebForm : System.Web.UI.Page
    {
        public static string ConnectionString { get; set; }

        protected void Page_Load(object sender, EventArgs e)
        {
            string name = Request.Form["product_name"];
            using (SqlConnection connection = new SqlConnection(ConnectionString))
            {
                SqlCommand sqlCommand = new SqlCommand()
                {
                    CommandText = "sp_GetProductIdFromName",
                    CommandType = CommandType.StoredProcedure,
                };

                sqlCommand.Parameters.Add("@productName", SqlDbType.NVarChar, 128).Value = name;

                SqlDataReader reader = sqlCommand.ExecuteReader();
            }
        }
    }
}
```

```vb
Imports System
Imports System.Data
Imports System.Data.SqlClient
Imports System.Linq

Namespace VulnerableWebApp
    Partial Public Class WebForm
        Inherits System.Web.UI.Page

        Public Property ConnectionString As String

        Protected Sub Page_Load(sender As Object, e As EventArgs)
            Dim name As String = Me.Request.Form("product_name")
            Using connection As SqlConnection = New SqlConnection(ConnectionString)
                Dim sqlCommand As SqlCommand = New SqlCommand With {.CommandText = "sp_GetProductIdFromName",
                                                                    .CommandType = CommandType.StoredProcedure}
                sqlCommand.Parameters.Add("@productName", SqlDbType.NVarChar, 128).Value = name
                Dim reader As SqlDataReader = sqlCommand.ExecuteReader()
            End Using
        End Sub
    End Class
End Namespace
```
