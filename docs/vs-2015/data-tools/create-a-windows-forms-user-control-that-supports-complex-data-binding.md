---
title: 複合データ バインディングをサポートする Windows フォーム ユーザー コントロールの作成 |Microsoft Docs
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
- data binding, user controls
- data binding, complex
- user controls [Visual Studio], complex data binding
ms.assetid: c8f29c2b-b49b-4618-88aa-33b6105880b5
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 6b263dd4e00fcb7a519ab89ecc693bd6216e0eeb
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60097155"
---
# <a name="create-a-windows-forms-user-control-that-supports-complex-data-binding"></a>複合データ バインディングをサポートする Windows フォーム ユーザー コントロールの作成
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Windows アプリケーションのフォームにデータを表示する場合は、**[ツールボックス]** から既存のコントロールを選択するか、またはアプリケーションが標準コントロールでは提供できない機能を必要とする場合は、カスタム コントロールを記述できます。 このチュートリアルでは、<xref:System.ComponentModel.ComplexBindingPropertiesAttribute> を実装するコントロールを作成する方法を示します。 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> を実装するコントロールには、データにバインドできる `DataSource` プロパティと `DataMember` プロパティが含まれます。 このようなコントロールは、<xref:System.Windows.Forms.DataGridView> や <xref:System.Windows.Forms.ListBox> に似ています。  
  
 コントロールの作成の詳細については、次を参照してください。[デザイン時に Windows フォーム コントロールの開発](http://msdn.microsoft.com/library/e5a8e088-7ec8-4fd9-bcb3-9078fd134829)します。  
  
 データ バインディングのシナリオで使用するためのコントロールを作成するときは、次のいずれかのデータ バインディング属性を実装する必要があります。  
  
|データ バインディング属性の使用方法|  
|-----------------------------------|  
|単一のデータ列またはプロパティを表示する <xref:System.ComponentModel.DefaultBindingPropertyAttribute> のような <xref:System.Windows.Forms.TextBox> を簡単なコントロールに実装します。 詳細については、次を参照してください。[単純データ バインディングをサポートする Windows フォーム ユーザー コントロール作成](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md)です。|  
|データの一覧またはテーブルを表示する <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> のような <xref:System.Windows.Forms.DataGridView> をコントロールに実装します。 このチュートリアルでは、このプロセスについて説明します。|  
|データの一覧またはテーブルを表示しますが、単一の列またはプロパティを表示する必要もある <xref:System.ComponentModel.LookupBindingPropertiesAttribute> のような <xref:System.Windows.Forms.ComboBox> をコントロールに実装します。 詳細については、次を参照してください。[ルックアップ データ バインディングをサポートする Windows フォーム ユーザー コントロール作成](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)です。|  
  
 このチュートリアルでは、テーブルからのデータ行を表示する複合コントロールを作成します。 この例では、Northwind サンプル データベースの `Customers` テーブルを使用します。 複合ユーザー コントロールは、カスタム コントロールの <xref:System.Windows.Forms.DataGridView> で Customers テーブルを表示します。  
  
 このチュートリアルでは、次の作業を行う方法について説明します。  
  
- 新規作成**Windows アプリケーション**します。  
  
- 新しい**ユーザー コントロール**をプロジェクトに追加します。  
  
- ユーザー コントロールをビジュアルに設計します。  
  
- `ComplexBindingProperty` 属性を実装します。  
  
- 使用してデータセットを作成、[データ ソース構成ウィザード](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)します。  
  
- 設定、**顧客**テーブルに、[データ ソース ウィンドウ](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)新しい複雑なコントロールを使用します。  
  
- 新しいコントロールをドラッグしてから、追加、**データ ソース ウィンドウ**に**Form1**します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを完了するための要件は次のとおりです。  
  
- Northwind サンプル データベースにアクセスします。
  
## <a name="create-a-windows-application"></a>Windows アプリケーションを作成します。  
 作成するには、まず、 **Windows アプリケーション**します。  
  
#### <a name="to-create-the-new-windows-project"></a>新しい Windows プロジェクトを作成するには  
  
1. Visual Studio から、**ファイル**] メニューの [新規作成**プロジェクト**します。  
  
2. プロジェクトに **ComplexControlWalkthrough** という名前を付けます。  
  
3. 選択**Windows アプリケーション**、 をクリック**OK**します。 詳細については、次を参照してください。[クライアント アプリケーション](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)します。  
  
     **ComplexControlWalkthrough** プロジェクトが作成されて**ソリューション エクスプローラー**に追加されます。  
  
## <a name="add-a-user-control-to-the-project"></a>プロジェクトにユーザー コントロールを追加する  
 このチュートリアルから複雑なデータ バインド コントロールが作成されるため、**ユーザー コントロール**、追加する必要があります、**ユーザー コントロール**をプロジェクトに項目。  
  
#### <a name="to-add-a-user-control-to-the-project"></a>プロジェクトにユーザー コントロールを追加するには  
  
1. **[プロジェクト]** メニューの **[ユーザー コントロールの追加]** を選択します。  
  
2. **[ファイル名]** 領域に「**ComplexDataGridView**」と入力し、**[追加]** をクリックします。  
  
     **ComplexDataGridView** コントロールが**ソリューション エクスプローラー**に追加され、デザイナーが開きます。  
  
## <a name="design-the-complexdatagridview-control"></a>ComplexDataGridView コントロールをデザインします。  
 この手順では、ユーザー コントロールに <xref:System.Windows.Forms.DataGridView> を追加します。  
  
#### <a name="to-design-the-complexdatagridview-control"></a>ComplexDataGridView コントロールを設計するには  
  
- **ツールボックス**からユーザー コントロールのデザイン サーフェイスに <xref:System.Windows.Forms.DataGridView> をドラッグします。  
  
## <a name="add-the-required-data-binding-attribute"></a>必要なデータ バインディング属性を追加します。  
 データ バインディングをサポートする複合コントロールには、<xref:System.ComponentModel.ComplexBindingPropertiesAttribute> を実装できます。  
  
#### <a name="to-implement-the-complexbindingproperties-attribute"></a>ComplexBindingProperties 属性を実装するには  
  
1. **ComplexDataGridView** コントロールをコード ビューに切り替えます  (**[表示]** メニューの **[コード]** を選択します)。  
  
2. `ComplexDataGridView` のコードを次のコードで置き換えます。  
  
     [!code-csharp[VbRaddataDisplaying#4](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDisplaying/CS/ComplexDataGridView.cs#4)]
     [!code-vb[VbRaddataDisplaying#4](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDisplaying/VB/ComplexDataGridView.vb#4)]  
  
3. **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
## <a name="creating-a-data-source-from-your-database"></a>データベースからデータ ソースの作成  
 この手順では、**データ ソース構成**ウィザードを使用して、Northwind サンプル データベースの `Customers` テーブルに基づいてデータ ソースを作成します。 接続を作成するには、Northwind サンプル データベースへのアクセス権を持っている必要があります。 Northwind サンプル データベースのセットアップについては、次を参照してください。[サンプル データベースの SQL Server のインストール](../data-tools/install-sql-server-sample-databases.md)します。  
  
#### <a name="to-create-the-data-source"></a>データ ソースを作成するには  
  
1. **[データ]** メニューの **[データ ソースの表示]** をクリックします。  
  
2. **[データ ソース]** ウィンドウで、**[新しいデータ ソースの追加]** をクリックして**データ ソース構成**ウィザードを起動します。  
  
3. **[データソースの種類を選択]** ページで、 **[データベース]** をクリックし、 **[次へ]** をクリックします。  
  
4. **[データ接続の選択]** ページで、次のいずれかの操作を行います。  
  
    - Northwind サンプル データベースへのデータ接続がドロップダウン リストに表示されている場合は選択します。  
  
    - **[新しい接続]** を選択して **[接続の追加] または [接続の変更]** ダイアログ ボックスを表示します。  
  
5. データベースにパスワードが必要な場合は、該当するオプションを選択して重要情報を含め、**[次へ]** をクリックします。  
  
6. **[アプリケーション構成ファイルに接続文字列を保存]** ページで、**[次へ]** をクリックします。  
  
7. **[データベース オブジェクトの選択]** ページで、**[テーブル]** ノードを展開します。  
  
8. `Customers` テーブルを選択し、**[完了]** をクリックします。  
  
     プロジェクトに **NorthwindDataSet** が追加され、**[データ ソース]** ウィンドウに `Customers` テーブルが表示されます。  
  
## <a name="set-the-customers-table-to-use-the-complexdatagridview-control"></a>ComplexDataGridView コントロールを使用して Customers テーブルを設定します。  
 **[データ ソース]** ウィンドウでは、フォームにコントロールをドラッグする前に作成するコントロールを設定できます。  
  
#### <a name="to-set-the-customers-table-to-bind-to-the-complexdatagridview-control"></a>Customers テーブルを ComplexDataGridView コントロールにバインドするように設定するには  
  
1. デザイナーで **Form1** を開きます。  
  
2. **[データ ソース]** ウィンドウの **[Customers]** ノードを展開します。  
  
3. **[Customers]** ノードのドロップダウン矢印をクリックし、**[カスタマイズ]** をクリックします。  
  
4. **[データ UI カスタマイズ オプション]** ダイアログ ボックスの **[関連付けられたコントロール]** の一覧の **[ComplexDataGridView]** を選択します。  
  
5. `Customers` テーブルのドロップダウン矢印をクリックし、コントロール リストから **ComplexDataGridView** を選択します。  
  
## <a name="addcontrols-to-the-form"></a>フォームに Addcontrols  
 **[データ ソース]** ウィンドウからフォームに項目をドラッグして、データ バインド コントロールを作成します。  
  
#### <a name="to-create-data-bound-controls-on-the-form"></a>フォームにデータ バインド コントロールを作成するには  
  
- メインのドラッグ**顧客**ノードから、**データ ソース**ウィンドウから、フォームにします。いることを確認、 **ComplexDataGridView**テーブルのデータを表示するコントロールを使用します。  
  
## <a name="running-the-application"></a>アプリケーションの実行  
  
#### <a name="to-run-the-application"></a>アプリケーションを実行するには  
  
- F5 キーを押してアプリケーションを実行します。  
  
## <a name="next-steps"></a>次の手順  
 アプリケーションの要件に応じて、データ バインディングをサポートするコントロールの作成後に、追加の操作を実行できます。 次の手順として、一般的には、次のようなことを実行します。  
  
- 他のアプリケーションで再利用できるように、コントロール ライブラリにカスタム コントロールを配置します。  
  
- 検索のシナリオをサポートするコントロールを作成します。 詳細については、次を参照してください。[ルックアップ データ バインディングをサポートする Windows フォーム ユーザー コントロール作成](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)です。  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio でのデータへの Windows フォーム コントロールのバインド](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [データ ソース ウィンドウからドラッグするときに作成されるコントロールを設定します。](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)   
 [Windows フォーム コントロール](http://msdn.microsoft.com/library/f050de8f-4ebd-4042-94b8-edf9a1dbd52a)
