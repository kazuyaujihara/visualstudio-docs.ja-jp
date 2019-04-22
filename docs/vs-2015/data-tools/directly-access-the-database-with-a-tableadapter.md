---
title: TableAdapter でデータベースに直接アクセス |Microsoft Docs
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
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5226f5c235b3af10fba4fd0fab3ee44ceb72a93e
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59654101"
---
# <a name="directly-access-the-database-with-a-tableadapter"></a>TableAdapter で直接データベースにアクセスする
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

加え、 `InsertCommand`、 `UpdateCommand`、および`DeleteCommand`Tableadapter は、データベースに対して直接実行できるメソッドで作成されます。 これらのメソッド (`TableAdapter.Insert`、 `TableAdapter.Update`、および`TableAdapter.Delete`) データベースで直接データの操作を呼び出すことができます。  
  
 これらのダイレクト メソッドを作成しない場合は、設定、TableAdapter の`GenerateDbDirectMethods`プロパティを`false`で、**プロパティ**ウィンドウ。 TableAdapter のメイン クエリだけでなく、TableAdapter にクエリを追加する場合は、これらの DbDirect メソッドを生成しないスタンドアロン クエリになります。  
  
## <a name="sendcommandsdirectly-to-a-database"></a>データベースに Sendcommandsdirectly  
 実行しようとするタスクを実行する TableAdapter の DbDirect メソッドを呼び出します。  
  
#### <a name="to-insert-new-records-directly-into-a-database"></a>データベースに直接新しいレコードを挿入するには  
  
-   呼び出す TableAdapter の`Insert`メソッド、パラメーターとして各列の値で渡します。 次の手順を使用して、`Region`例をテーブルに Northwind databaseas にします。  
  
    > [!NOTE]
    >  使用可能なインスタンスがいない場合は、TableAdapter を使用するをインスタンス化します。  
  
     [!code-csharp[VbRaddataSaving#15](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#15)]
     [!code-vb[VbRaddataSaving#15](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#15)]  
  
#### <a name="to-update-records-directly-in-a-database"></a>データベースに直接レコードを更新するには  
  
-   呼び出す TableAdapter の`Update`メソッド、パラメーターとして各列の新しいと、元の値を渡します。  
  
    > [!NOTE]
    >  使用可能なインスタンスがいない場合は、TableAdapter を使用するをインスタンス化します。  
  
     [!code-csharp[VbRaddataSaving#18](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#18)]
     [!code-vb[VbRaddataSaving#18](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#18)]  
  
#### <a name="to-delete-records-directly-from-a-database"></a>データベースから直接レコードを削除するには  
  
-   呼び出す TableAdapter の`Delete`メソッドのパラメーターとして各列の値を渡す、`Delete`メソッド。 次の手順を使用して、`Region`例をテーブルに Northwind databaseas にします。  
  
    > [!NOTE]
    >  使用可能なインスタンスがいない場合は、TableAdapter を使用するをインスタンス化します。  
  
     [!code-csharp[VbRaddataSaving#21](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#21)]
     [!code-vb[VbRaddataSaving#21](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>関連項目  
 [TableAdapters を使用してデータセットを入力する](../data-tools/fill-datasets-by-using-tableadapters.md)
