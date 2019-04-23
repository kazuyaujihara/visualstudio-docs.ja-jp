---
title: TableAdapter で直接データベースにアクセスする
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Visual Basic], accessing with a TableAdapter
- DBDirect methods
- datasets [Visual Basic], adding to projects
- data [Visual Studio], saving
- TableAdapter.Delete method
- GenerateDbDirectMethods property
- TableAdapter.Insert method
- TableAdapter.GenerateDBDirectMethods property
- TableAdapter.Update method
- saving data
- TableAdapters
ms.assetid: 012c5924-91f7-4790-b2a6-f51402b7014b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 26bcab8d589c1fedcbbc4eb1f8b06bb1c04cac53
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60113301"
---
# <a name="directly-access-the-database-with-a-tableadapter"></a>TableAdapter で直接データベースにアクセスする

加え、 `InsertCommand`、 `UpdateCommand`、および`DeleteCommand`Tableadapter は、データベースに対して直接実行できるメソッドで作成されます。 これらのメソッドを呼び出すことができます (`TableAdapter.Insert`、 `TableAdapter.Update`、および`TableAdapter.Delete`) データベースで直接データを操作します。

これらのダイレクト メソッドを作成しない場合は、設定、TableAdapter の`GenerateDbDirectMethods`プロパティを`false`で、**プロパティ**ウィンドウ。 TableAdapter のメイン クエリだけでなく、TableAdapter にクエリを追加する場合はこれらを生成しないスタンドアロン クエリ`DbDirect`メソッド。

## <a name="send-commands-directly-to-a-database"></a>データベースに直接コマンドを送信します。

TableAdapter を呼び出す`DbDirect`実現しようとしているタスクを実行するメソッド。

### <a name="to-insert-new-records-directly-into-a-database"></a>データベースに直接新しいレコードを挿入するには

- 呼び出す TableAdapter の`Insert`メソッド、パラメーターとして各列の値で渡します。 次の手順を使用して、`Region`例として、Northwind データベースのテーブル。

    > [!NOTE]
    > 使用可能なインスタンスがいない場合は、TableAdapter を使用するをインスタンス化します。

     [!code-vb[VbRaddataSaving#15](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_1.vb)]
     [!code-csharp[VbRaddataSaving#15](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_1.cs)]

### <a name="to-update-records-directly-in-a-database"></a>データベースに直接レコードを更新するには

- 呼び出す TableAdapter の`Update`メソッド、パラメーターとして各列の新しいと、元の値を渡します。

    > [!NOTE]
    > 使用可能なインスタンスがいない場合は、TableAdapter を使用するをインスタンス化します。

     [!code-vb[VbRaddataSaving#18](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_2.vb)]
     [!code-csharp[VbRaddataSaving#18](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_2.cs)]

### <a name="to-delete-records-directly-from-a-database"></a>データベースから直接レコードを削除するには

- 呼び出す TableAdapter の`Delete`メソッドのパラメーターとして各列の値を渡す、`Delete`メソッド。 次の手順を使用して、`Region`例として、Northwind データベースのテーブル。

    > [!NOTE]
    > 使用可能なインスタンスがいない場合は、TableAdapter を使用するをインスタンス化します。

     [!code-vb[VbRaddataSaving#21](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_3.vb)]
     [!code-csharp[VbRaddataSaving#21](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_3.cs)]

## <a name="see-also"></a>関連項目

- [TableAdapters を使用してデータセットを入力する](../data-tools/fill-datasets-by-using-tableadapters.md)