---
title: 新しいレコードをデータベースに挿入する |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- TableAdapters, inserting new records into
- data [Visual Studio], saving
- databases, inserting new records into
- records, inserting
- saving data
ms.assetid: ea118fff-69b1-4675-b79a-e33374377f04
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3c686a764f42f50a3e59da3e8b37b219ddb7b11c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72651560"
---
# <a name="insert-new-records-into-a-database"></a>データベースに新しいレコードを挿入する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

新しいレコードをデータベースに挿入するには、`TableAdapter.Update` メソッド、または TableAdapter の DBDirect メソッド (具体的には `TableAdapter.Insert` メソッド) のいずれかを使用できます。

 アプリケーションで Tableadapter を使用しない場合は、コマンドオブジェクト (<xref:System.Data.SqlClient.SqlCommand> など) を使用してデータベースに新しいレコードを挿入できます。

 アプリケーションでデータセットを使用してデータを格納する場合は、`TableAdapter.Update` メソッドを使用します。 @No__t_0 メソッドは、すべての変更 (更新、挿入、および削除) をデータベースに送信します。

 アプリケーションでオブジェクトを使用してデータを格納する場合、またはデータベースで新しいレコードの作成をより細かく制御する必要がある場合は、`TableAdapter.Insert` メソッドを使用します。

 TableAdapter に `Insert` メソッドがない場合は、TableAdapter がストアドプロシージャを使用するように構成されているか、その `GenerateDBDirectMethods` プロパティが `false` に設定されていることを意味します。 データセットデザイナー内から TableAdapter の `GenerateDBDirectMethods` プロパティを `true` に設定し、データセットを保存します。 これにより、TableAdapter が再生成されます。 TableAdapter に `Insert` メソッドがまだない場合、テーブルには、個々の行を区別するための十分なスキーマ情報が得られない可能性があります (たとえば、テーブルに主キーが設定されていない可能性があります)。

## <a name="insert-new-records-by-using-tableadapters"></a>Tableadapter を使用して新しいレコードを挿入する
 Tableadapter には、アプリケーションの要件に応じて、データベースに新しいレコードを挿入するためのさまざまな方法が用意されています。

 アプリケーションでデータセットを使用してデータを格納する場合は、単にデータセット内の目的の <xref:System.Data.DataTable> に新しいレコードを追加し、`TableAdapter.Update` メソッドを呼び出すことができます。 @No__t_0 メソッドは、<xref:System.Data.DataTable> 内のすべての変更をデータベースに送信します (変更されたレコードと削除されたレコードを含む)。

#### <a name="to-insert-new-records-into-a-database-by-using-the-tableadapterupdate-method"></a>TableAdapter. Update メソッドを使用して新しいレコードをデータベースに挿入するには

1. 新しい <xref:System.Data.DataRow> を作成して <xref:System.Data.DataTable.Rows%2A> コレクションに追加することで、目的の <xref:System.Data.DataTable> に新しいレコードを追加します。 詳細については、「[方法: DataTable に行を追加](https://msdn.microsoft.com/library/78ebbb43-c402-49cf-81da-0715289487bf)する」を参照してください。

2. 新しい行が <xref:System.Data.DataTable> に追加されたら、`TableAdapter.Update` メソッドを呼び出します。 更新するデータの量を制御するには、<xref:System.Data.DataSet> 全体、<xref:System.Data.DataTable>、<xref:System.Data.DataRow>s の配列、または1つの <xref:System.Data.DataRow> を渡します。

    次のコードは、<xref:System.Data.DataTable> に新しいレコードを追加し、`TableAdapter.Update` メソッドを呼び出して、新しい行をデータベースに保存する方法を示しています。 (この例では、Northwind データベースの `Region` テーブルを使用しています)。

    [!code-csharp[VbRaddataSaving#14](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form5.cs#14)]
    [!code-vb[VbRaddataSaving#14](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form5.vb#14)]

   アプリケーションでオブジェクトを使用してデータを格納している場合は、`TableAdapter.Insert` メソッドを使用して、データベースに直接新しい行を作成できます。 @No__t_0 メソッドは、各列の個別の値をパラメーターとして受け取ります。 メソッドを呼び出すと、渡されたパラメーター値を使用して新しいレコードがデータベースに挿入されます。

   次の手順では、Northwind データベースの `Region` テーブルを例として使用します。

#### <a name="to-insert-new-records-into-a-database-by-using-the-tableadapterinsert-method"></a>TableAdapter. Insert メソッドを使用して新しいレコードをデータベースに挿入するには

- TableAdapter の `Insert` メソッドを呼び出し、各列の値をパラメーターとして渡します。

    > [!NOTE]
    > 使用可能なインスタンスがない場合は、使用する TableAdapter をインスタンス化します。

     [!code-csharp[VbRaddataSaving#15](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#15)]
     [!code-vb[VbRaddataSaving#15](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#15)]

## <a name="insert-new-records-by-using-command-objects"></a>コマンドオブジェクトを使用して新しいレコードを挿入する
 次の例では、コマンドオブジェクトを使用して、新しいレコードをデータベースに直接挿入します。

 次の手順では、Northwind データベースの `Region` テーブルを例として使用します。

#### <a name="to-insert-new-records-into-a-database-by-using-command-objects"></a>コマンドオブジェクトを使用して新しいレコードをデータベースに挿入するには

- 新しい command オブジェクトを作成し、その `Connection`、`CommandType`、および `CommandText` の各プロパティを設定します。

     [!code-csharp[VbRaddataSaving#16](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#16)]
     [!code-vb[VbRaddataSaving#16](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#16)]

## <a name="net-framework-security"></a>.NET Framework セキュリティ
 接続しようとしているデータベースへのアクセス権と、目的のテーブルに挿入を実行する権限が必要です。

## <a name="see-also"></a>参照
 [データをデータベースに保存する](../data-tools/save-data-back-to-the-database.md)
