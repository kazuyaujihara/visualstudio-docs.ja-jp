---
title: TableAdapter を使用してデータを更新する
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], saving
- data [Visual Studio], TableAdapters
- updating data, TableAdapters
- TableAdapters, updating data
- data [Visual Studio], updating
- saving data
ms.assetid: 5e32e10e-9bac-4969-9bdd-b8f6919d3516
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 61ebcd6c833b55f0769365b89274e35136c914f9
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68925346"
---
# <a name="update-data-by-using-a-tableadapter"></a>TableAdapter を使用してデータを更新する

データセット内のデータを変更および検証した後は、 `Update` [TableAdapter](../data-tools/create-and-configure-tableadapters.md)のメソッドを呼び出すことによって、更新されたデータをデータベースに戻すことができます。 メソッド`Update`は、1つのデータテーブルを更新し、テーブル内の各データ行<xref:System.Data.DataRow.RowState%2A>のに基づいて、適切なコマンド (INSERT、UPDATE、または DELETE) を実行します。 データセットに関連テーブルがある場合、Visual Studio によって、更新を実行するために使用する TableAdapterManager クラスが生成されます。 TableAdapterManager クラスは、データベースで定義されている外部キー制約に基づいて、更新が正しい順序で行われることを保証します。 データバインドコントロールを使用すると、データバインディングアーキテクチャによって tableAdapterManager という TableAdapterManager クラスのメンバー変数が作成されます。

> [!NOTE]
> データセットの内容を使用してデータソースを更新しようとすると、エラーが発生することがあります。 エラーを回避するには、 `Update`アダプターのメソッドを呼び出すコードを`catch`ブロック`try` /内に配置することをお勧めします。

データソースを更新するための正確な手順は、ビジネスニーズによって異なりますが、次の手順が含まれます。

1. `Update`ブロックでアダプターの/メソッドを呼び出します。 `try` `catch`

2. 例外が検出された場合は、エラーを引き起こしたデータ行を探します。

3. データ行の問題を調整する (可能な場合はプログラムによって、ユーザーに無効な行を表示することによって変更する場合)<xref:System.Data.DataRow.HasErrors%2A>、 <xref:System.Data.DataTable.GetErrors%2A>もう一度更新を実行します (、)。

## <a name="save-data-to-a-database"></a>データベースにデータを保存する

TableAdapter の`Update`メソッドを呼び出します。 データベースに書き込まれる値を含むデータテーブルの名前を渡します。

### <a name="to-update-a-database-by-using-a-tableadapter"></a>TableAdapter を使用してデータベースを更新するには

- TableAdapter の`Update`メソッドを/ `try` ブロック`catch`で囲みます。 次の例では`Customers` 、内`NorthwindDataSet`のテーブルの内容を`catch`ブロック内`try` /から更新する方法を示します。

     [!code-csharp[VbRaddataSaving#9](../data-tools/codesnippet/CSharp/update-data-by-using-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataSaving#9](../data-tools/codesnippet/VisualBasic/update-data-by-using-a-tableadapter_1.vb)]

## <a name="see-also"></a>関連項目

- [データをデータベースに保存する](../data-tools/save-data-back-to-the-database.md)