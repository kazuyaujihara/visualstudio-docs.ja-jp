---
title: TableAdapter DBDirect メソッドを使ってデータを保存 |Microsoft Docs
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
- TableAdapters, walkthroughs
- data [Visual Studio], saving
- saving data, walkthroughs
- data [Visual Studio], TableAdapter
ms.assetid: 74a6773b-37e1-4d96-a39c-63ee0abf49b1
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7cba6f91dd6dc0bb826531a312dc6ca5c94b21a5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62558743"
---
# <a name="save-data-with-the-tableadapter-dbdirect-methods"></a>TableAdapter DBDirect メソッドを使用してデータを保存する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このチュートリアルでは、TableAdapter の DBDirect メソッドを使用して、データベースに対して直接 SQL ステートメントを実行するための詳細な手順を提供します。 TableAdapter の DBDirect メソッドを使用すると、データベースの更新をきめ細かいレベルで制御できます。 それらを使用するには個別に呼び出すことによって、特定の SQL ステートメントおよびストアド プロシージャを実行する`Insert`、 `Update`、および`Delete`アプリケーションに必要なメソッド (オーバー ロードされたのではなく`Update`更新プログラムを実行するメソッド、INSERT、および 1 回の呼び出しですべての DELETE ステートメント)。  
  
 このチュートリアルでは、次の作業を行う方法について説明します。  
  
- 新規作成**Windows アプリケーション**します。  
  
- 作成し、構成を含むデータセット、[データ ソース構成ウィザード](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)します。  
  
- **[データ ソース]** ウィンドウから項目をドラッグしたときにフォーム上に作成されるコントロールを選択します。 詳細については、次を参照してください。[設定、データ ソース ウィンドウからドラッグするときに作成されるコントロール](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)します。  
  
- **[データ ソース]** ウィンドウからフォームに項目をドラッグして、データ バインド フォームを作成します。  
  
- 直接データベースにアクセスし、挿入、更新、および削除を実行するメソッドを追加するには.  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを完了するための要件は次のとおりです。  
  
- Northwind サンプル データベースにアクセスします。
  
## <a name="create-a-windows-application"></a>Windows アプリケーションを作成します。  
 作成するには、まず、 **Windows アプリケーション**します。  
  
#### <a name="to-create-the-new-windows-project"></a>新しい Windows プロジェクトを作成するには  
  
1. Visual Studio での**ファイル**] メニューの [新規作成**プロジェクト**。  
  
2. プロジェクトに名前を**TableAdapterDbDirectMethodsWalkthrough**します。  
  
3. 選択**Windows アプリケーション**、し、 **OK**します。 詳細については、次を参照してください。[クライアント アプリケーション](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)します。  
  
     **TableAdapterDbDirectMethodsWalkthrough** プロジェクトが作成されて**ソリューション エクスプローラー**に追加されます。  
  
## <a name="create-a-data-source-from-your-database"></a>データベースからデータ ソースを作成します。  
 この手順では、**データ ソース構成ウィザード**を使用して、Northwind サンプル データベースの `Region` テーブルに基づいてデータ ソースを作成します。 接続を作成するには、Northwind サンプル データベースへのアクセス権を持っている必要があります。
  
#### <a name="to-create-the-data-source"></a>データ ソースを作成するには  
  
1. **データ**メニューの  **データ ソースの**します。  
  
2. **[データ ソース]** ウィンドウで、**[新しいデータ ソースの追加]** をクリックして**データ ソース構成ウィザード**を起動します。  
  
3. **データ ソースの種類を選択**画面で、**データベース**、し、**次**します。  
  
4. **データ接続の選択**画面で、次のいずれかの操作を行います。  
  
    - Northwind サンプル データベースへのデータ接続がドロップダウン リストに表示されている場合は選択します。  
  
         - または -  
  
    - **[新しい接続]** を選択して **[接続の追加] または [接続の変更]** ダイアログ ボックスを表示します。  
  
5. データベースにパスワードが必要な場合は、機密データを含めるしを選択するオプションを選択**次**します。  
  
6. **接続文字列をアプリケーション構成ファイルに保存**画面で、**次**します。  
  
7. **データベース オブジェクトの選択**画面で、展開、**テーブル**ノード。  
  
8. 選択、`Region`テーブルし、**完了**します。  
  
     プロジェクトに **NorthwindDataSet** が追加され、**[データ ソース]** ウィンドウに `Region` テーブルが表示されます。  
  
## <a name="addcontrols-to-the-form-to-display-the-data"></a>データを表示するフォームに Addcontrols  
 **[データ ソース]** ウィンドウからフォームに項目をドラッグして、データ バインド コントロールを作成します。  
  
#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>Windows フォーム上のコントロールのバインドをデータを作成するには  
  
- メインのドラッグ**リージョン**ノードから、**データ ソース**ウィンドウから、フォームにします。  
  
     レコード間をナビゲートするための <xref:System.Windows.Forms.DataGridView> コントロールとツール ストリップ (<xref:System.Windows.Forms.BindingNavigator>) がフォームに表示されます。 A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)、RegionTableAdapter、 <xref:System.Windows.Forms.BindingSource>、および<xref:System.Windows.Forms.BindingNavigator>コンポーネント トレイに表示されます。  
  
#### <a name="to-add-buttons-that-will-call-the-individual-tableadapter-dbdirect-methods"></a>個々の TableAdapter DbDirect メソッドを呼び出すボタンを追加するには  
  
1. **ツールボックス**から 3 つの <xref:System.Windows.Forms.Button> コントロールを **RegionDataGridView** の下の **Form1** にドラッグします。  
  
2. 各ボタンの **[名前]** および **[テキスト]** プロパティを設定します。  
  
    |名前|テキスト|  
    |----------|----------|  
    |`InsertButton`|**[挿入]**|  
    |`UpdateButton`|**更新**|  
    |`DeleteButton`|**削除**|  
  
#### <a name="to-add-code-to-insert-new-records-into-the-database"></a>データベースに新しいレコードを挿入するコードを追加するには  
  
1. 選択**InsertButton**クリック イベントのイベント ハンドラーを作成し、コード エディターでフォームを開きます。  
  
2. `InsertButton_Click` イベント ハンドラーを次のコードで置き換えます。  
  
     [!code-csharp[VbRaddataSaving#1](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form1.cs#1)]
     [!code-vb[VbRaddataSaving#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form1.vb#1)]  
  
#### <a name="to-add-code-to-update-records-in-the-database"></a>データベースのレコードを更新するコードを追加するには  
  
1. **[UpdateButton]** をダブルクリックして、クリック イベントのイベント ハンドラーを作成し、コード エディターでフォームを開きます。  
  
2. `UpdateButton_Click` イベント ハンドラーを次のコードで置き換えます。  
  
     [!code-csharp[VbRaddataSaving#2](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form1.cs#2)]
     [!code-vb[VbRaddataSaving#2](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form1.vb#2)]  
  
#### <a name="to-add-code-to-delete-records-from-the-database"></a>データベースからレコードを削除するコードを追加するには  
  
1. 選択**DeleteButton**クリック イベントのイベント ハンドラーを作成し、コード エディターでフォームを開きます。  
  
2. `DeleteButton_Click` イベント ハンドラーを次のコードで置き換えます。  
  
     [!code-csharp[VbRaddataSaving#3](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form1.cs#3)]
     [!code-vb[VbRaddataSaving#3](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form1.vb#3)]  
  
## <a name="run-the-application"></a>アプリケーションの実行  
  
#### <a name="to-run-the-application"></a>アプリケーションを実行するには  
  
- 選択**F5**アプリケーションを実行します。  
  
- 選択、**挿入**ボタンをクリックし、新しいレコードがグリッドに表示されることを確認します。  
  
- 選択、 **Update**ボタンをクリックし、グリッドのレコードが更新されることを確認します。  
  
- 選択、**削除**ボタンをクリックし、グリッドからレコードが削除されることを確認します。  
  
## <a name="next-steps"></a>次の手順  
 アプリケーションの要件によっては、データ バインド フォームの作成後に実行する場合があります。 このチュートリアルで行うことができる拡張には次のものがあります。  
  
- フォームに検索機能を追加します。 詳細については、「[方法 :パラメーター化クエリを Windows フォーム アプリケーションを追加する](http://msdn.microsoft.com/library/13db4ad3-56b9-4a0b-b3a5-6a4ff84d4416)します。  
  
- **[データ ソース]** ウィンドウの **[ウィザードで DataSet を構成]** を選択して、データセットにテーブルを追加します。 関連するコードをフォームにドラッグすることによって、関連するデータを表示するコントロールを追加できます。 
  
## <a name="see-also"></a>関連項目  
 [データをデータベースに保存する](../data-tools/save-data-back-to-the-database.md)
