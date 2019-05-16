---
title: トランザクションでのデータの保存 |Microsoft Docs
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
- System.Transactions namespace
- data [Visual Studio], saving in a transaction
- transactions, saving data
- Transactions namespace
- saving data
ms.assetid: 80260118-08bc-4b37-bfe5-9422ee7a1e4e
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 08480e46ab492acb1c7ab10c8514897721708aba
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65692467"
---
# <a name="save-data-in-a-transaction"></a>トランザクションにデータを保存する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このチュートリアルを使用して、トランザクションでデータを保存する方法について説明、<xref:System.Transactions>名前空間。 この例では、Northwind サンプル データベースの `Customers` テーブルと `Orders` テーブルを使用します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルでは、Northwind サンプル データベースへのアクセスが必要です。
  
## <a name="create-a-windows-application"></a>Windows アプリケーションを作成します。  
 作成するには、まず、 **Windows アプリケーション**します。  
  
#### <a name="to-create-the-new-windows-project"></a>新しい Windows プロジェクトを作成するには  
  
1. Visual Studio での**ファイル**] メニューの [新規作成**プロジェクト**。  
  
2. プロジェクトに名前を**SavingDataInATransactionWalkthrough**します。  
  
3. 選択**Windows アプリケーション**、し、 **OK**します。 詳細については、次を参照してください。[クライアント アプリケーション](https://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)します。  
  
     **SavingDataInATransactionWalkthrough** プロジェクトが作成されて**ソリューション エクスプローラー**に追加されます。  
  
## <a name="create-a-database-data-source"></a>データベースのデータ ソースを作成します。  
 このステップでは、[データ ソース構成ウィザード](https://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)に基づいてデータ ソースを作成する、`Customers`と`Orders`Northwind サンプル データベース内のテーブル。  
  
#### <a name="to-create-the-data-source"></a>データ ソースを作成するには  
  
1. **データ**メニューの **データ ソースの**します。  
  
2. **[データ ソース]** ウィンドウで、**[新しいデータ ソースの追加]** をクリックして**データ ソース構成ウィザード**を起動します。  
  
3. **データ ソースの種類を選択**画面で、**データベース**、し、**次**します。  
  
4. **データ接続の選択**画面は、次のいずれか。  
  
    - Northwind サンプル データベースへのデータ接続がドロップダウン リストに表示されている場合は選択します。  
  
         - または -  
  
    - **[新しい接続]** を選択して **[接続の追加] または [接続の変更]** ダイアログ ボックスを表示し、Northwind データベースへの接続を作成します。  
  
5. データベースにパスワードが必要な場合は、機密データを含めるしを選択するオプションを選択**次**します。  
  
6. **接続文字列をアプリケーション構成ファイルに保存**画面で、**次**します。  
  
7. **データベース オブジェクトの選択**画面で、展開、**テーブル**ノード。  
  
8. 選択、`Customers`と`Orders`テーブル、および選択**完了**します。  
  
     プロジェクトに **NorthwindDataSet** が追加され、**[データ ソース]** ウィンドウに `Customers` テーブルと `Orders` テーブルが表示されます。  
  
## <a name="addcontrols-to-the-form"></a>フォームに Addcontrols  
 **[データ ソース]** ウィンドウからフォームに項目をドラッグして、データ バインド コントロールを作成します。  
  
#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>Windows フォーム上のコントロールのバインドをデータを作成するには  
  
- **データソース**ウィンドウで、展開、**顧客**ノード。  
  
- **[データ ソース]** ウィンドウから **Form1** にメインの **[Customers]** ノードをドラッグします。  
  
     レコード間をナビゲートするための <xref:System.Windows.Forms.DataGridView> コントロールとツール ストリップ (<xref:System.Windows.Forms.BindingNavigator>) がフォームに表示されます。 [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)、CustomersTableAdapter、<xref:System.Windows.Forms.BindingSource>、<xref:System.Windows.Forms.BindingNavigator> がコンポーネント トレイに表示されます。  
  
- 関連するドラッグ**注文**ノード (main ではない**注文**が関連する子テーブル ノードの下、 **Fax**列) 下のフォームに、 **CustomersDataGridView**します。  
  
     <xref:System.Windows.Forms.DataGridView> がフォームに表示されます。 OrdersTableAdapter と<xref:System.Windows.Forms.BindingSource>コンポーネント トレイに表示されます。  
  
## <a name="add-a-reference-to-the-systemtransactions-assembly"></a>System.Transactions アセンブリへの参照を追加します。  
 トランザクションは、<xref:System.Transactions> 名前空間を使用します。 System.Transactions アセンブリへの参照をプロジェクトは、手動で追加する必要があるため、既定では追加されません。  
  
#### <a name="to-add-a-reference-to-the-systemtransactions-dll-file"></a>System.Transactions の DLL ファイルへの参照を追加するには  
  
1. **プロジェクト**メニューの **参照の追加**します。  
  
2. 選択**System.Transactions**(上、 **.NET** ] タブ)、し、[ **[ok]** します。  
  
     **System.Transactions** への参照がプロジェクトに追加されます。  
  
## <a name="modifythe-code-in-the-bindingnavigators-saveitem-button"></a>BindingNavigator の SaveItem ボタンのコードを変更してはなりません。  
 既定でコードを追加、フォーム上にドロップされた最初のテーブルの`click`のボタンでは、保存のイベント、<xref:System.Windows.Forms.BindingNavigator>します。 追加テーブルを更新する場合は、手動でコードを追加する必要があります。 このチュートリアルでは、リファクタリング、既存のコードをファイルから保存ボタンの click イベント ハンドラー。また、行が追加または削除する必要があるかどうかに基づいて、特定の更新機能を提供するメソッドを作成します。  
  
#### <a name="to-modify-the-auto-generated-save-code"></a>自動生成された保存コードを変更するには  
  
1. 選択、**保存**のボタンでは、 **CustomersBindingNavigator** (フロッピー ディスクのアイコンのボタン)。  
  
2. `CustomersBindingNavigatorSaveItem_Click` メソッドを次のコードで置き換えます。  
  
    [!code-csharp[VbRaddataSaving#4](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form2.cs#4)]
    [!code-vb[VbRaddataSaving#4](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form2.vb#4)]  
  
   関連するデータへの変更を解決する順序は次のとおりです。  
  
- 子レコードを削除します。 (この場合、レコードを削除、`Orders`テーブルです)。  
  
- 親レコードを削除します。 (この場合、レコードを削除、`Customers`テーブルです)。  
  
- 親レコードを挿入します。(この場合は、内のレコードを挿入、`Customers`テーブルです)。  
  
- 子レコードを挿入します。 (この場合は、内のレコードを挿入、`Orders`テーブルです)。  
  
#### <a name="to-delete-existing-orders"></a>既存の注文を削除するには  
  
- 次の `DeleteOrders` メソッドを **Form1** に追加します。  
  
     [!code-csharp[VbRaddataSaving#5](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form2.cs#5)]
     [!code-vb[VbRaddataSaving#5](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form2.vb#5)]  
  
#### <a name="to-delete-existing-customers"></a>既存の顧客を削除するには  
  
- 次の `DeleteCustomers` メソッドを **Form1** に追加します。  
  
     [!code-csharp[VbRaddataSaving#6](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form2.cs#6)]
     [!code-vb[VbRaddataSaving#6](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form2.vb#6)]  
  
#### <a name="to-add-new-customers"></a>新規顧客を追加するには  
  
- 次の `AddNewCustomers` メソッドを **Form1** に追加します。  
  
     [!code-csharp[VbRaddataSaving#7](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form2.cs#7)]
     [!code-vb[VbRaddataSaving#7](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form2.vb#7)]  
  
#### <a name="to-add-new-orders"></a>新規注文を追加するには  
  
- 次の `AddNewOrders` メソッドを **Form1** に追加します。  
  
     [!code-csharp[VbRaddataSaving#8](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form2.cs#8)]
     [!code-vb[VbRaddataSaving#8](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form2.vb#8)]  
  
## <a name="run-the-application"></a>アプリケーションの実行  
  
#### <a name="to-run-the-application"></a>アプリケーションを実行するには  
  
- 選択**F5**アプリケーションを実行します。  
  
## <a name="see-also"></a>関連項目  
 [データをデータベースに保存する](../data-tools/save-data-back-to-the-database.md)
