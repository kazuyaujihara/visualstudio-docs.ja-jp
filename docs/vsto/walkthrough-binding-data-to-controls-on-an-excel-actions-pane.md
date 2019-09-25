---
title: 'チュートリアル: Excel 操作ウィンドウのコントロールにデータをバインドする'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], data binding
- actions panes [Office development in Visual Studio], data binding
- data binding [Office development in Visual Studio], smart documents
- data binding [Office development in Visual Studio], actions panes
- actions panes [Office development in Visual Studio], binding controls
- smart documents [Office development in Visual Studio], data binding
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 1543f872961d556674dd5ad6b3f5b8071d2d404b
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71253881"
---
# <a name="walkthrough-bind-data-to-controls-on-an-excel-actions-pane"></a>チュートリアル: Excel 操作ウィンドウのコントロールにデータをバインドする
  このチュートリアルでは Microsoft Office Excel の操作ウィンドウ上のコントロールへのデータバインドについて説明します。 このコントロールは、SQL Server データベースのテーブル間のマスター/詳細の関係を示します。

 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]

 このチュートリアルでは、次の作業について説明します。

- ワークシートにコントロールを追加する。

- 操作ウィンドウコントロールを作成しています。

- 操作ウィンドウコントロールへのデータバインド Windows フォームコントロールの追加。

- アプリケーションが開いたときに操作ウィンドウを表示します。

> [!NOTE]
> 次の手順で参照している Visual Studio ユーザー インターフェイス要素の一部は、お使いのコンピューターでは名前や場所が異なる場合があります。 これらの要素は、使用している Visual Studio のエディションや独自の設定によって決まります。 詳細については、「[Visual Studio IDE のカスタマイズ](../ide/personalizing-the-visual-studio-ide.md)」を参照してください。

## <a name="prerequisites"></a>必須コンポーネント
 このチュートリアルを実行するには、次のコンポーネントが必要です。

- [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]

- [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] または [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]。

- Northwind SQL Server サンプルデータベースを使用したサーバーへのアクセス。

- SQL Server データベースに対する読み取りと書き込みの権限。

## <a name="create-the-project"></a>プロジェクトの作成
 まず、Excel ブック プロジェクトを作成します。

### <a name="to-create-a-new-project"></a>新しいプロジェクトを作成するには

1. " **My Excel Actions Pane**" という名前の excel ブックプロジェクトを作成します。 ウィザードで、 **[新しいドキュメントの作成]** を選択します。 詳細については、「[方法 :Visual Studio で Office プロジェクトを作成する方法](../vsto/how-to-create-office-projects-in-visual-studio.md)」を参照してください。

     新しい Excel ブックがデザイナーで開き、 **[My Excel Actions] ウィンドウ**プロジェクトが**ソリューションエクスプローラー**に追加されます。

## <a name="add-a-new-data-source-to-the-project"></a>新しいデータソースをプロジェクトに追加する

### <a name="to-add-a-new-data-source-to-the-project"></a>新しいデータソースをプロジェクトに追加するには

1. **[データソース]** ウィンドウが表示されていない場合は、メニューバーの [**他の Windows** > **データソース**の**表示** > ] をクリックして表示します。

2. **[新しいデータ ソースの追加]** をクリックして **データ ソース構成ウィザード**を開始します。

3. **[データベース]** を選択し、 **[次へ]** をクリックします。

4. Northwind サンプル SQL Server データベースへのデータ接続を選択するか、 **[新しい接続]** ボタンを使用して新しい接続を追加します。

5. **[次へ]** をクリックします。

6. 選択されている場合は、接続を保存するオプションをオフにして、 **[次へ]** をクリックします。

7. **[データベースオブジェクト]** ウィンドウで、 **[テーブル]** ノードを展開します。

8. **[仕入先]** テーブルの横にあるチェックボックスをオンにします。

9. **Products**テーブルを展開し、 **ProductName**、**仕入**先、 **QuantityPerUnit**、および**UnitPrice**を選択します。

10. **[完了]** をクリックします。

    ウィザードにより、 **[データソース]** ウィンドウに [**仕入先**テーブルと**製品**] テーブルが追加されます。 また、**ソリューションエクスプローラー**に表示される、型指定されたデータセットをプロジェクトに追加します。

## <a name="add-controls-to-the-worksheet"></a>ワークシートにコントロールを追加する
 次に、最初<xref:Microsoft.Office.Tools.Excel.NamedRange>のワークシート<xref:Microsoft.Office.Tools.Excel.ListObject>にコントロールとコントロールを追加します。

### <a name="to-add-a-namedrange-control-and-a-listobject-control"></a>NamedRange コントロールと ListObject コントロールを追加するには

1. **[My Excel Actions]** \ (Excel の操作 \) `Sheet1`ブックが Visual Studio デザイナーで開かれていることを確認します。

2. **[データソース]** ウィンドウで、 **[仕入先]** テーブルを展開します。

3. **[会社名]** ノードのドロップダウン矢印をクリックし、 **[NamedRange]** をクリックします。

4. **[データソース]** ウィンドウから [ `Sheet1`**会社名**] をセル**A2**にドラッグします。

     という名前`CompanyNameNamedRange`の\<コントロールが作成され、セル A2 にテキスト CompanyName > が表示されます。 <xref:Microsoft.Office.Tools.Excel.NamedRange> 同時に、と<xref:System.Data.DataSet> `suppliersBindingSource` <xref:System.Windows.Forms.BindingSource>いう名前の、テーブルアダプター、およびがプロジェクトに追加されます。 コントロールは、 <xref:System.Windows.Forms.BindingSource>にバインドされ、さらに<xref:System.Data.DataSet>インスタンスにバインドされます。

5. **[データソース]** ウィンドウで、 **[仕入先]** テーブルの下にある列を下にスクロールします。 一覧の一番下には**Products**テーブルがあります。これは、**仕入先**テーブルの子であるためです。 **[仕入先]** テーブルと同じレベルにある この **[製品]** テーブルを選択し、表示されるドロップダウン矢印をクリックします。

6. ドロップダウンリストで **[ListObject]** をクリックし、 **Products**テーブルをの`Sheet1`セル**A6**にドラッグします。

     という名前`ProductNameListObject`のコントロールがセル A6 に作成されます<xref:Microsoft.Office.Tools.Excel.ListObject> 。 同時に、と`productsBindingSource` いう名前のテーブルアダプターがプロジェクトに追加されます。<xref:System.Windows.Forms.BindingSource> コントロールは、 <xref:System.Windows.Forms.BindingSource>にバインドされ、さらに<xref:System.Data.DataSet>インスタンスにバインドされます。

7. のC#場合のみ、コンポーネントトレイの **[suppliersBindingSource]** を選択し、 **[プロパティ]** ウィンドウで **[修飾子]** プロパティを **[内部]** に変更します。

## <a name="add-controls-to-the-actions-pane"></a>[操作] ウィンドウにコントロールを追加する
 次に、コンボボックスを持つ操作ウィンドウコントロールが必要です。

### <a name="to-add-an-actions-pane-control"></a>操作ウィンドウコントロールを追加するには

1. **ソリューションエクスプローラー**で **[My Excel Actions] ウィンドウ**プロジェクトを選択します。

2. **[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。

3. **[新しい項目の追加]** ダイアログボックスで **[操作ウィンドウコントロール]** を選択し、「 **ActionsControl**」という名前を指定して、 **[追加]** をクリックします。

### <a name="to-add-data-bound-windows-forms-controls-to-an-actions-pane-control"></a>データバインド Windows フォームコントロールを操作ウィンドウコントロールに追加するには

1. **[ツールボックス]** の [ <xref:System.Windows.Forms.ComboBox> **コモンコントロール**] タブから、[操作] ウィンドウコントロールにコントロールをドラッグします。

2. **Size**プロパティを**171, 21**に変更します。

3. コンボボックスに合わせてユーザーコントロールのサイズを変更します。

## <a name="bind-the-control-on-the-actions-pane-to-data"></a>操作ウィンドウのコントロールをデータにバインドする
 このセクションでは、のデータソースを、 <xref:System.Windows.Forms.ComboBox>ワークシート上の<xref:Microsoft.Office.Tools.Excel.NamedRange>コントロールと同じデータソースに設定します。

### <a name="to-set-data-binding-properties-of-the-control"></a>コントロールのデータバインディングプロパティを設定するには

1. 操作 ウィンドウコントロールを右クリックし、**コードの表示** をクリックします。

2. [操作] ウィンドウコントロールの<xref:System.Windows.Forms.UserControl.Load>イベントに次のコードを追加します。

     [!code-vb[Trin_VstcoreActionsPaneExcel#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ActionsControl.vb#1)]
     [!code-csharp[Trin_VstcoreActionsPaneExcel#1](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ActionsControl.cs#1)]

3. でC#は、 `ActionsControl`のイベントハンドラーを作成する必要があります。 このコードは、 `ActionsControl`コンストラクターに配置できます。 イベントハンドラーの作成の詳細について[は、「」を参照してください。Office プロジェクト](../vsto/how-to-create-event-handlers-in-office-projects.md)でイベントハンドラーを作成します。

     [!code-csharp[Trin_VstcoreActionsPaneExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ActionsControl.cs#2)]

## <a name="show-the-actions-pane"></a>操作ウィンドウを表示する
 実行時にコントロールを追加するまで、[操作] ウィンドウは表示されません。

#### <a name="to-show-the-actions-pane"></a>操作ウィンドウを表示するには

1. **ソリューションエクスプローラー**で、[ *ThisWorkbook* ] または [ *ThisWorkbook.cs*] を右クリックし、 **[コードの表示]** をクリックします。

2. `ThisWorkbook`クラスにユーザーコントロールの新しいインスタンスを作成します。

     [!code-csharp[Trin_VstcoreActionsPaneExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#3)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#3)]

3. <xref:Microsoft.Office.Tools.Excel.Workbook.Startup> の`ThisWorkbook`イベントハンドラーで、[操作] ウィンドウにコントロールを追加します。

     [!code-csharp[Trin_VstcoreActionsPaneExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#4)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#4)]

## <a name="test-the-application"></a>アプリケーションをテストする
 ドキュメントをテストして、ドキュメントを開いたときに操作ウィンドウが開いていること、およびコントロールにマスター/詳細関係があることを確認できるようになりました。

### <a name="to-test-your-document"></a>文書をテストするには

1. **F5**キーを押して、プロジェクトを実行します。

2. 操作ウィンドウが表示されていることを確認します。

3. リストボックスで会社を選択します。 <xref:Microsoft.Office.Tools.Excel.NamedRange>コントロールに会社名が表示されていること、および製品の詳細が<xref:Microsoft.Office.Tools.Excel.ListObject>コントロールに表示されていることを確認します。

4. 会社名と製品詳細が必要に応じて変更されていることを確認するには、さまざまな企業を選択します。

## <a name="next-steps"></a>次の手順
 ここでは、次の作業を行います。

- Word のコントロールへのデータのバインド 詳細については、「[チュートリアル:Word の操作ウィンドウ](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md)上のコントロールにデータをバインドします。

- プロジェクトを配置しています。 詳細については、「 [ClickOnce を使用した Office ソリューションの配置](../vsto/deploying-an-office-solution-by-using-clickonce.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [操作ウィンドウの概要](../vsto/actions-pane-overview.md)
- [方法: 操作ウィンドウのコントロールのレイアウトを管理する](../vsto/how-to-manage-control-layout-on-actions-panes.md)
- [Office ソリューションのコントロールにデータをバインドする](../vsto/binding-data-to-controls-in-office-solutions.md)
