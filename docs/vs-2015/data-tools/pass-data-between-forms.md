---
title: フォーム間でデータを渡す |Microsoft Docs
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
- walkthroughs [Windows Forms], data
- walkthroughs [Visual Studio], data
- data [Visual Studio], passing between forms
- forms, passing data between
- Windows Forms, walkthroughs
ms.assetid: 78bf038b-9296-4fbf-b0e8-d881d1aff0df
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9a109490c4ff89c6a9f45533fc1305d915522621
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59668939"
---
# <a name="pass-data-between-forms"></a>フォーム間でデータを渡す
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このチュートリアルでは、フォーム間でデータを渡す手順について説明します。 顧客と Northwind の orders テーブルを使用して、1 つの形式は、ユーザーが顧客を選択して、2 番目の形式は、選択した顧客の注文を表示します。 このチュートリアルでは、最初のフォームからデータを受信する 2 番目の形式でメソッドを作成する方法を示します。  
  
> [!NOTE]
>  このチュートリアルでは、フォーム間でデータを渡す 1 つの方法についてのみ説明します。 データを受信する 2 つ目のコンス トラクターの作成など、フォームにデータを渡すためには、その他のオプションがあるか、最初のフォームからデータをパブリック プロパティの作成を設定できます。  
  
 このチュートリアルでは、以下のタスクを行います。  
  
-   新しいを作成する**Windows アプリケーション**プロジェクト。  
  
-   作成と構成を含むデータセット、[データ ソース構成ウィザード](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)します。  
  
-   **[データ ソース]** ウィンドウから項目をドラッグしたときにフォーム上に作成するコントロールを選択します。 詳細については、次を参照してください。[設定、データ ソース ウィンドウからドラッグするときに作成されるコントロール](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)します。  
  
-   **[データ ソース]** ウィンドウからフォームに項目をドラッグして、データ バインド コントロールを作成します。  
  
-   データを表示するグリッドのある 2 番目のフォームを作成します。  
  
-   特定の顧客の注文をフェッチする TableAdapter クエリを作成します。  
  
-   フォーム間でデータを渡します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを完了するための要件は次のとおりです。  
  
-   Northwind サンプル データベースにアクセスします。
  
## <a name="create-the-windows-application"></a>Windows アプリケーションを作成します。  
  
#### <a name="to-create-the-new-windows-project"></a>新しい Windows プロジェクトを作成するには  
  
1.  **ファイル**] メニューの [新しいプロジェクトを作成します。  
  
2.  プロジェクトに `PassingDataBetweenForms` という名前を付けます。  
  
3.  選択**Windows フォーム アプリケーション**、 をクリック**OK**します。 詳細については、次を参照してください。[クライアント アプリケーション](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)します。  
  
     **PassingDataBetweenForms** プロジェクトが作成され、**ソリューション エクスプローラー**に追加されます。  
  
## <a name="create-the-data-source"></a>データ ソースを作成します。  
  
#### <a name="to-create-the-data-source"></a>データ ソースを作成するには  
  
1.  **[データ]** メニューの **[データ ソースの表示]** をクリックします。  
  
2.  **[データ ソース]** ウィンドウで、**[新しいデータ ソースの追加]** をクリックして**データ ソース構成**ウィザードを起動します。  
  
3.  **[データソースの種類を選択]** ページで、 **[データベース]** をクリックし、 **[次へ]** をクリックします。  
  
4.  **[データベース モデルの選択]** ページで、**[データセット]** が指定されていることを確認し、**[次へ]** をクリックします。  
  
5.  **[データ接続の選択]** ページで、次のいずれかの操作を行います。  
  
    -   Northwind サンプル データベースへのデータ接続がドロップダウン リストに表示されている場合は選択します。  
  
    -   **[新しい接続]** を選択して **[接続の追加] または [接続の変更]** ダイアログ ボックスを表示します。  
  
6.  データベースにパスワードが必要であり、重要情報を含めるオプションを有効にする場合は、このオプションを選択し、**[次へ]** をクリックします。  
  
7.  **[アプリケーション構成ファイルに接続文字列を保存]** ページで、**[次へ]** をクリックします。  
  
8.  **[データベース オブジェクトの選択]** ページで、**[テーブル]** ノードを展開します。  
  
9. **Customers** テーブルと **Orders** テーブルを選択し、**[完了]** をクリックします。  
  
     プロジェクトに **NorthwindDataSet** が追加され、**[データ ソース]** ウィンドウに **Customers** テーブルと **Orders** テーブルが表示されます。  
  
## <a name="create-the-first-form-form1"></a>最初のフォーム (Form1) を作成します。  
 **[データ ソース]** ウィンドウから **Customers** ノードをフォームにドラッグして、データ バインド グリッド (<xref:System.Windows.Forms.DataGridView> コントロール) を作成します。  
  
#### <a name="to-create-a-data-bound-grid-on-the-form"></a>フォームにデータ バインド グリッドを作成するには  
  
-   **[データ ソース]** ウィンドウから **Form1** にメインの **[Customers]** ノードをドラッグします。  
  
     <xref:System.Windows.Forms.DataGridView> と、レコード間を移動するためのツール ストリップ (<xref:System.Windows.Forms.BindingNavigator>) が **Form1** 上に表示されます。 [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)、CustomersTableAdapter、<xref:System.Windows.Forms.BindingSource>、<xref:System.Windows.Forms.BindingNavigator> がコンポーネント トレイに表示されます。  
  
## <a name="create-the-second-form-form2"></a>2 番目のフォーム (Form2) を作成します。  
  
#### <a name="to-create-a-second-form-to-pass-the-data-to"></a>データの渡し先となる 2 番目のフォームを作成するには  
  
1.  **[プロジェクト]** メニューの **[Windows フォームの追加]** を選択します。  
  
2.  名前を既定の **Form2** のままにして、**[追加]** をクリックします。  
  
3.  **[データ ソース]** ウィンドウから **Form2** にメインの **[Orders]** ノードをドラッグします。  
  
     <xref:System.Windows.Forms.DataGridView> と、レコード間を移動するためのツール ストリップ (<xref:System.Windows.Forms.BindingNavigator>) が **Form2** 上に表示されます。 [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)、CustomersTableAdapter、<xref:System.Windows.Forms.BindingSource>、<xref:System.Windows.Forms.BindingNavigator> がコンポーネント トレイに表示されます。  
  
4.  コンポーネント トレイから **OrdersBindingNavigator** を削除します。  
  
     **Form2** から **OrdersBindingNavigator** が消えます。  
  
## <a name="add-a-tableadapter-query-to-form2-to-load-orders-for-the-selected-customer-on-form1"></a>Form2 を Form1 で選択した顧客の注文を読み込む TableAdapter クエリを追加します。  
  
#### <a name="to-create-a-tableadapter-query"></a>TableAdapter クエリを作成するには  
  
1.  **ソリューション エクスプローラー**で、**NorthwindDataSet.xsd** ファイルをダブルクリックします。  
  
2.  **[OrdersTableAdapter]** を右クリックし、**[クエリの追加]** を選択します。  
  
3.  **[SQL ステートメントを使用する]** を既定のオプションのままにして、**[次へ]** をクリックします。  
  
4.  **[複数行を返す SELECT]** を既定のオプションのままにして、**[次へ]** をクリックします。  
  
5.  `CustomerID` に基づいて `Orders` を返すために、クエリに WHERE 句を追加します。 クエリは次のようになります。  
  
    ```  
    SELECT OrderID, CustomerID, EmployeeID, OrderDate, RequiredDate, ShippedDate, ShipVia, Freight, ShipName, ShipAddress, ShipCity, ShipRegion, ShipPostalCode, ShipCountry  
    FROM Orders   
    WHERE CustomerID = @CustomerID  
    ```  
  
    > [!NOTE]
    >  データベースに対してパラメーターの構文が正しいことを確認します。 たとえば、Microsoft Access では、WHERE 句は `WHERE CustomerID = ?` のようになります。  
  
6.  **[次へ]** をクリックします。  
  
7.  **DataTableMethod 名前を入力**、型`FillByCustomerID`します。  
  
8.  **[DataTable を返す]** オプションをオフにして、**[次へ]** をクリックします。  
  
9. **[完了]** をクリックします。  
  
## <a name="create-a-method-on-form2-to-pass-data-to"></a>データの渡し先となる Form2 のメソッドを作成します。  
  
#### <a name="to-create-a-method-to-pass-data-to"></a>データの渡し先となるメソッドを作成するには  
  
1.  **Form2** を右クリックし、**[コードの表示]** を選択して**コード エディター**で **Form2** を開きます。  
  
2.  **Form2** の `Form2_Load` メソッドの後に次のコードを追加します。  
  
     [!code-csharp[VbRaddataDisplaying#1](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDisplaying/CS/Form2.cs#1)]
     [!code-vb[VbRaddataDisplaying#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDisplaying/VB/Form2.vb#1)]  
  
## <a name="create-a-method-on-form1-to-pass-data-and-display-form2"></a>データを渡して、Form2 を表示する Form1 のメソッドを作成します。  
  
#### <a name="to-create-a-method-to-pass-data-to-form2"></a>Form2 にデータを渡すメソッドを作成するには  
  
1.  **Form1** の Customer データ グリッドを右クリックし、**[プロパティ]** をクリックします。  
  
2.  **[プロパティ]** ウィンドウで、**[イベント]** をクリックします。  
  
3.  **CellDoubleClick** イベントをダブルクリックします。  
  
     コード エディターが表示されます。  
  
4.  メソッド定義を次のサンプルのように更新します。  
  
     [!code-csharp[VbRaddataDisplaying#2](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDisplaying/CS/Form1.cs#2)]
     [!code-vb[VbRaddataDisplaying#2](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDisplaying/VB/Form1.vb#2)]  
  
## <a name="run-the-application"></a>アプリケーションを実行する  
  
#### <a name="to-run-the-application"></a>アプリケーションを実行するには  
  
-   F5 キーを押してアプリケーションを実行します。  
  
-   **Form1** で顧客レコードをダブルクリックして、その顧客の注文を表示する **Form2** を開きます。  
  
## <a name="next-steps"></a>次の手順  
 フォーム間でデータを渡した後に、アプリケーションの要件に応じてさらに操作を追加して実行できます。 このチュートリアルで行うことができる拡張には次のものがあります。  
  
-   データセットを編集し、データベース オブジェクトの追加または削除を行います。 詳細については、[データセットの作成と構成](../data-tools/create-and-configure-datasets-in-visual-studio.md)に関するページを参照してください。  
  
-   データベースにデータを戻して保存する機能を追加します。 詳細については、次を参照してください。[データをデータベースに保存](../data-tools/save-data-back-to-the-database.md)します。  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio でのデータへの Windows フォーム コントロールのバインド](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
