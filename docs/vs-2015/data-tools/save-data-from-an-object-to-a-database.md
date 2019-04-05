---
title: オブジェクトからデータベースにデータを保存 |Microsoft Docs
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
- data [Visual Studio], saving
- data access [Visual Studio], objects
- saving data
ms.assetid: efd6135a-40cf-4b0d-8f8b-41a5aaea7057
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4ddb6ad55a8d90a3e9d4f5b2568885cbe49fb66c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58972406"
---
# <a name="save-data-from-an-object-to-a-database"></a>オブジェクトからデータベースにデータを保存する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
TableAdapter の DBDirect メソッドのいずれかに、オブジェクトから値を渡すことでオブジェクトをデータベースでデータを保存することができます (たとえば、 `TableAdapter.Insert`)。
  
 オブジェクトのコレクションからデータを保存するには、オブジェクト (次のループなど) のコレクションをループ処理し、TableAdapter の DBDirect メソッドのいずれかを使用して、各オブジェクトの値をデータベースに送信します。  
  
 既定では、データベースに対して直接実行できる TableAdapter の DBDirect メソッドが作成されます。 これらのメソッドは、直接呼び出すことができ、必要としない<xref:System.Data.DataSet>または<xref:System.Data.DataTable>データベースへの更新を送信するために変更を調整するオブジェクト。  
  
> [!NOTE]
>  TableAdapter を構成するとき、メインのクエリは DBDirect メソッドを作成するのに十分な情報を提供する必要があります。 たとえば、TableAdapter が定義されている主キー列がないテーブルからデータのクエリに構成されている場合に生成しません DBDirect メソッド。  
  
|TableAdapter DBDirect メソッド|説明|  
|----------------------------------|-----------------|  
|`TableAdapter.Insert`|データベースに新しいレコードを追加して、個々 の列の値をメソッド パラメーターとして渡すことができます。|  
|`TableAdapter.Update`|既存のデータベース内のレコードを更新します。 `Update`メソッドはメソッドのパラメーターとしての元と新しい列の値を受け取ります。 元のレコードを検索するため、元の値と新しい値は、そのレコードの更新に使用されます。<br /><br /> `TableAdapter.Update`ことで、元のデータベースにデータセットの変更を調整するメソッドを使用しても、 <xref:System.Data.DataSet>、 <xref:System.Data.DataTable>、 <xref:System.Data.DataRow>、または配列の<xref:System.Data.DataRow>メソッドのパラメーターとして。|  
|`TableAdapter.Delete`|メソッドのパラメーターとして渡された元の列の値に基づいて、データベースから既存のレコードを削除します。|  
  
### <a name="to-save-new-records-from-an-object-to-a-database"></a>オブジェクトから新しいレコードをデータベースに保存するには  
  
-   値を渡すことによって、レコードを作成、`TableAdapter.Insert`メソッド。  
  
     次の例は、新しい顧客レコードを作成、`Customers`テーブル内の値を渡すことによって、`currentCustomer`オブジェクトを`TableAdapter.Insert`メソッド。  
  
     [!code-csharp[VbRaddataSaving#23](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form3.cs#23)]
     [!code-vb[VbRaddataSaving#23](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form3.vb#23)]  
  
### <a name="to-update-existing-records-from-an-object-to-a-database"></a>オブジェクトからデータベースへの既存のレコードを更新するには  
  
-   呼び出すことによって、レコードの変更、`TableAdapter.Update`メソッドをレコードを更新する新しい値を渡すと、レコードを検索する元の値を渡します。  
  
    > [!NOTE]
    >  オブジェクトに渡すために、元の値を維持するために必要のある、`Update`メソッド。 この例でのプロパティを使用して、`orig`元の値を格納するプレフィックス。  
  
     次の例の既存のレコードを更新する、`Customers`テーブル内の新しいバージョンと元の値を渡すことによって、`Customer`オブジェクトを`TableAdapter.Update`メソッド。  
  
     [!code-csharp[VbRaddataSaving#24](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form3.cs#24)]
     [!code-vb[VbRaddataSaving#24](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form3.vb#24)]  
  
### <a name="to-delete-existing-records-from-a-database"></a>既存のレコードをデータベースから削除するには  
  
-   呼び出すことにより、レコードを削除、`TableAdapter.Delete`メソッドとレコードを検索する元の値を渡すことです。  
  
    > [!NOTE]
    >  オブジェクトに渡すために、元の値を維持するために必要のある、`Delete`メソッド。 この例でのプロパティを使用して、`orig`元の値を格納するプレフィックス。  
  
     次の例からのレコードの削除、`Customers`テーブルの元の値を渡すことによって、`Customer`オブジェクトを`TableAdapter.Delete`メソッド。  
  
     [!code-csharp[VbRaddataSaving#25](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form3.cs#25)]
     [!code-vb[VbRaddataSaving#25](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form3.vb#25)]  
  
## <a name="net-framework-security"></a>.NET Framework セキュリティ  
 選択の挿入を実行する権限が必要更新、またはデータベースのテーブルを削除します。  
  
## <a name="see-also"></a>関連項目  
 [データをデータベースに保存する](../data-tools/save-data-back-to-the-database.md)
