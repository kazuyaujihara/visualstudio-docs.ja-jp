---
title: データを検索する Windows フォームの作成 |Microsoft Docs
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
- Windows Forms, searching data
- Windows Forms, displaying data
- parameters, displaying filtered data
- data [Visual Studio], parameterizing queries
- data [Visual Studio], searching
ms.assetid: 65ca79a9-7458-466c-af55-978cd24c549e
caps.latest.revision: 31
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cd800e5d31189487689781c1f04cd82479893dfa
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58974558"
---
# <a name="create-a-windows-form-to-search-data"></a>データを検索する Windows フォームを作成する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
一般的なアプリケーションのシナリオでは、選択したデータをフォーム上に表示します。 たとえば、特定の顧客の注文、特定の注文の明細などを表示する場合があります。 このシナリオでは、ユーザーがフォームに情報を入力した後、ユーザーの入力をパラメーターとして使用してクエリが実行されます。つまり、パラメーター クエリに基づいてデータが選択されます。 クエリは、ユーザーが入力した条件を満たすデータのみを返します。 ここでは、特定の都市にいる顧客を返すクエリを作成する方法、およびユーザー インターフェイスを変更して、ユーザーが都市の名前を入力してクエリを実行するボタンを押すことができるようにする方法について説明します。  
  
 パラメーター クエリを使用することにより、データベースが最も得意とする作業 (レコードの迅速なフィルター処理) をデータベースに任せることができるため、アプリケーションの効率が高まります。 一方、データベース テーブル全体を要求し、それをネットワークを通じて転送し、アプリケーション ロジックを使用して必要なレコードを見つける場合は、アプリケーションが低速になり、効率が低下する可能性があります。  
  
 パラメーター化クエリを追加するには、TableAdapter (およびコントロール パラメーターの値をそのまま使用し、クエリを実行する) を使用して、**検索条件ビルダー**  ダイアログ ボックス。 このダイアログ ボックスを開くには、**[データ]** メニュー (または TableAdapter スマート タグ) の **[クエリの追加]** をクリックします。  
  
 このチュートリアルでは、以下のタスクを行います。  
  
-   新しい Windows フォーム アプリケーション プロジェクトを作成します。  
  
-   使用してアプリケーションでのデータ ソースの構成の作成と、**データ ソースの構成**ウィザード。  
  
-   内の項目のドロップ タイプを設定、**データソース**ウィンドウ。  
  
-   **[データ ソース]** ウィンドウからフォームに項目をドラッグし、データを表示するコントロールを作成します。  
  
-   データを表示するコントロールをフォームに追加します。  
  
-   完了、**検索条件ビルダー**  ダイアログ ボックス。  
  
-   フォームにパラメーターを入力し、パラメーター化クエリを実行します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを完了するための要件は次のとおりです。  
  
-   Northwind サンプル データベースにアクセスします。  
  
## <a name="create-the-windows-application"></a>Windows アプリケーションを作成します。  
 作成するには、まず、 **Windows アプリケーション**します。 プロジェクトに名前を割り当てるはこの手順で、省略可能ですが、名前を付けますが、ここでため、後で保存します。  
  
#### <a name="to-create-the-new-windows-application-project"></a>新しい Windows アプリケーション プロジェクトを作成するには  
  
1.  **ファイル**] メニューの [新しいプロジェクトを作成します。  
  
2.  プロジェクトに `WindowsSearchForm` という名前を付けます。  
  
3.  選択**Windows アプリケーション** をクリック**OK**します。  
  
     **WindowsSearchForm** プロジェクトが作成されて**ソリューション エクスプローラー**に追加されます。  
  
## <a name="create-the-data-source"></a>データ ソースを作成します。  
 この手順を使用してデータベースからのデータ ソースの作成、**データ ソースの構成**ウィザード。 接続を作成するには、Northwind サンプル データベースへのアクセス権を持っている必要があります。 Northwind サンプル データベースのセットアップについては、次を参照してください。[サンプル データベースの SQL Server のインストール](../data-tools/install-sql-server-sample-databases.md)します。  
  
#### <a name="to-create-the-data-source"></a>データ ソースを作成するには  
  
1.  **[データ]** メニューの **[データ ソースの表示]** をクリックします。  
  
2.  **[データ ソース]** ウィンドウで、**[新しいデータ ソースの追加]** をクリックして**データ ソース構成**ウィザードを起動します。  
  
3.  **[データソースの種類を選択]** ページで、 **[データベース]** をクリックし、 **[次へ]** をクリックします。  
  
4.  **[データ接続の選択]** ページで、次のいずれかの操作を行います。  
  
    -   Northwind サンプル データベースへのデータ接続がドロップダウン リストに表示されている場合は選択します。  
  
    -   **[新しい接続]** を選択して **[接続の追加] または [接続の変更]** ダイアログ ボックスを表示します。  
  
5.  データベースにパスワードが必要な場合は、該当するオプションを選択して重要情報を含め、**[次へ]** をクリックします。  
  
6.  **[アプリケーション構成ファイルに接続文字列を保存]** ページで、**[次へ]** をクリックします。  
  
7.  **[データベース オブジェクトの選択]** ページで、**[テーブル]** ノードを展開します。  
  
8.  **Customers** テーブルを選択し、**[完了]** をクリックします。  
  
     プロジェクトに **NorthwindDataSet** が追加され、**[データ ソース]** ウィンドウに **Customers** テーブルが表示されます。  
  
## <a name="create-the-form"></a>フォームを作成します。  
 **[データ ソース]** ウィンドウからフォームに項目をドラッグして、データ バインド コントロールを作成します。  
  
#### <a name="to-create-data-bound-controls-on-the-form"></a>フォームにデータ バインド コントロールを作成するには  
  
1.  **[データ ソース]** ウィンドウの **[Customers]** ノードを展開します。  
  
2.  **[Customers]** ノードを **[データ ソース]** ウィンドウからフォームにドラッグします。  
  
     <xref:System.Windows.Forms.DataGridView> と、レコード間を移動するためのツール ストリップ (<xref:System.Windows.Forms.BindingNavigator>) がフォーム上に表示されます。 [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)、CustomersTableAdapter、<xref:System.Windows.Forms.BindingSource>、<xref:System.Windows.Forms.BindingNavigator> がコンポーネント トレイに表示されます。  
  
## <a name="addparameterization-search-functionality-to-the-query"></a>クエリに Addparameterization (検索機能)  
 WHERE 句を追加するには元のクエリを使用する、**検索条件ビルダー**  ダイアログ ボックス。  
  
#### <a name="to-create-a-parameterized-query-and-controls-to-enter-the-parameters"></a>パラメーター クエリとコントロールを作成してパラメーターを入力するには  
  
1.  <xref:System.Windows.Forms.DataGridView> コントロールを選択し、**[データ]** メニューの **[クエリの追加]** をクリックします。  
  
2.  型`FillByCity`で、**新しいクエリ名**上の領域、**検索条件ビルダー**  ダイアログ ボックス。  
  
3.  **[クエリ テキスト]** 領域でクエリに `WHERE City = @City` を追加します。  
  
     クエリは次のようになります。  
  
     `SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax`  
  
     `FROM Customers`  
  
     `WHERE City = @City`  
  
    > [!NOTE]
    >  アクセスおよび OLE DB データ ソースは疑問符 () を使用して ('? ') パラメーターを示すためにそのため、WHERE 句はようになります:`WHERE City = ?`します。  
  
4.  **[OK]** をクリックして **[検索条件ビルダー]** ダイアログ ボックスを閉じます。  
  
     **FillByCityToolStrip** がフォームに追加されます。  
  
## <a name="testing-the-application"></a>アプリケーションのテスト  
 アプリケーションを実行すると、パラメーターを入力として取得できる状態のフォームが開きます。  
  
#### <a name="to-test-the-application"></a>アプリケーションをテストするには  
  
1.  F5 キーを押してアプリケーションを実行します。  
  
2.  **[City]** ボックスに「**London**」と入力し、**[FillByCity]** をクリックします。  
  
     データ グリッドには、条件を満たす顧客が取得されます。 この例では、**[City]** 列の値が **London** の顧客だけがデータ グリッドに表示されます。  
  
## <a name="next-steps"></a>次の手順  
 アプリケーションの要件に応じて、パラメーター付きのフォームを作成した後に、追加の操作を実行できます。 このチュートリアルで行うことができる拡張には次のものがあります。  
  
-   関連するデータを表示するコントロールを追加します。  
  
-   データセットを編集し、データベース オブジェクトの追加または削除を行います。 詳細については、[データセットの作成と構成](../data-tools/create-and-configure-datasets-in-visual-studio.md)に関するページを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio でのデータへの Windows フォーム コントロールのバインド](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
