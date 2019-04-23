---
title: 単純データ バインディングをサポートする Windows フォーム ユーザー コントロールの作成 |Microsoft Docs
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
- custom controls [Visual Studio], Data Sources Window
- Data Sources Window, controls
ms.assetid: b1488366-6dfb-454e-9751-f42fd3f3ddfb
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: dc14e8751e11c53bb43041228a6556604d0d9641
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59664756"
---
# <a name="create-a-windows-forms-user-control-that-supports-simple-data-binding"></a>単純なデータ バインディングをサポートする Windows フォーム ユーザー コントロールの作成
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Windows アプリケーションのフォームにデータを表示する場合は、**[ツールボックス]** から既存のコントロールを選択するか、またはアプリケーションが標準コントロールでは提供できない機能を必要とする場合は、カスタム コントロールを記述できます。 このチュートリアルでは、<xref:System.ComponentModel.DefaultBindingPropertyAttribute> を実装するコントロールを作成する方法を示します。 <xref:System.ComponentModel.DefaultBindingPropertyAttribute> を実装するコントロールには、データにバインドできるプロパティを 1 つ含めることができます。 このようなコントロールは、<xref:System.Windows.Forms.TextBox> や <xref:System.Windows.Forms.CheckBox> に似ています。  
  
 コントロールの作成の詳細については、次を参照してください。[デザイン時に Windows フォーム コントロールの開発](http://msdn.microsoft.com/library/e5a8e088-7ec8-4fd9-bcb3-9078fd134829)します。  
  
 データ バインディングのシナリオで使用するためのコントロールを作成するときに、次のデータ バインディング属性のいずれかを実装する必要があります。  
  
|データ バインディング属性の使用方法|  
|-----------------------------------|  
|単一のデータ列またはプロパティを表示する <xref:System.ComponentModel.DefaultBindingPropertyAttribute> のような <xref:System.Windows.Forms.TextBox> を簡単なコントロールに実装します。 このチュートリアルでは、このプロセスについて説明します。|  
|データの一覧またはテーブルを表示する <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> のような <xref:System.Windows.Forms.DataGridView> をコントロールに実装します。 詳細については、次を参照してください。[複合データ バインディングをサポートする Windows フォーム ユーザー コントロール作成](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)です。|  
|データの一覧またはテーブルを表示しますが、単一の列またはプロパティを表示する必要もある <xref:System.ComponentModel.LookupBindingPropertiesAttribute> のような <xref:System.Windows.Forms.ComboBox> をコントロールに実装します。 詳細については、次を参照してください。[ルックアップ データ バインディングをサポートする Windows フォーム ユーザー コントロール作成](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)です。|  
  
 このチュートリアルでは、テーブルの単一の列のデータを表示する簡単なコントロールを作成します。 この例では、Northwind サンプル データベースの `Phone` テーブルの `Customers` 列を使用します。 単純なユーザー コントロールを使用して、標準の電話番号形式で顧客の電話番号を表示するが、<xref:System.Windows.Forms.MaskedTextBox>電話番号にマスクを設定するとします。  
  
 このチュートリアルでは、次の作業を行う方法について説明します。  
  
-   新規作成**Windows アプリケーション**します。  
  
-   新しい**ユーザー コントロール**をプロジェクトに追加します。  
  
-   ユーザー コントロールをビジュアルに設計します。  
  
-   `DefaultBindingProperty` 属性を実装します。  
  
-   使用してデータセットを作成、**データ ソースの構成**ウィザード。  
  
-   **[データ ソース]** ウィンドウで **[Phone]** 列が新しいコントロールを使用するように設定します。  
  
-   フォームを作成して、新しいコントロールにデータを表示します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを完了するための要件は次のとおりです。  
  
-   Northwind サンプル データベースにアクセスします。
  
## <a name="create-a-windows-application"></a>Windows アプリケーションを作成します。  
 作成するには、まず、 **Windows アプリケーション**します。  
  
#### <a name="to-create-the-new-windows-project"></a>新しい Windows プロジェクトを作成するには  
  
1.  Visual Studio から、**ファイル**] メニューの [新規作成**プロジェクト**します。  
  
2.  プロジェクトに名前を**SimpleControlWalkthrough**します。  
  
3.  選択**Windows アプリケーション** をクリック**OK**します。 詳細については、次を参照してください。[クライアント アプリケーション](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)します。  
  
     **SimpleControlWalkthrough** プロジェクトが作成されて**ソリューション エクスプローラー**に追加されます。  
  
## <a name="add-a-user-control-to-the-project"></a>プロジェクトにユーザー コントロールを追加する  
 このチュートリアルから単純なデータ バインド可能なコントロールを作成、**ユーザー コントロール**、ため、追加、**ユーザー コントロール**項目を**SimpleControlWalkthrough**プロジェクト。  
  
#### <a name="to-add-a-user-control-to-the-project"></a>プロジェクトにユーザー コントロールを追加するには  
  
1.  **[プロジェクト]** メニューの **[ユーザー コントロールの追加]** を選択します。  
  
2.  型`PhoneNumberBox`名 をクリックします**追加**します。  
  
     **PhoneNumberBox** コントロールが **ソリューション エクスプローラー**に追加され、デザイナーが開きます。  
  
## <a name="design-the-phonenumberbox-control"></a>PhoneNumberBox コントロールをデザインします。  
 このチュートリアルでは、既存の <xref:System.Windows.Forms.MaskedTextBox> を展開して `PhoneNumberBox` コントロールを作成します。  
  
#### <a name="to-design-the-phonenumberbox-control"></a>PhoneNumberBox コントロールを設計するには  
  
1.  **ツールボックス**からユーザー コントロールのデザイン サーフェイスに <xref:System.Windows.Forms.MaskedTextBox> をドラッグします。  
  
2.  ドラッグした <xref:System.Windows.Forms.MaskedTextBox> のスマート タグを選択し、**[マスクの設定]** を選択します。  
  
3.  **[定型入力]** ダイアログ ボックスで **[電話番号]** を選択し、**[OK]** をクリックしてマスクを設定します。  
  
## <a name="add-the-required-data-binding-attribute"></a>必要なデータ バインディング属性を追加します。  
 データ バインディングをサポートする簡単なコントロールに対しては <xref:System.ComponentModel.DefaultBindingPropertyAttribute> を実装します。  
  
#### <a name="to-implement-the-defaultbindingproperty-attribute"></a>DefaultBindingProperty 属性を実装するには  
  
1.  `PhoneNumberBox` コントロールをコード ビューに切り替えます。 (**[表示]** メニューの **[コード]** を選択します。)  
  
2.  `PhoneNumberBox` のコードを次のコードで置き換えます。  
  
     [!code-csharp[VbRaddataDisplaying#3](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDisplaying/CS/PhoneNumberBox.cs#3)]
     [!code-vb[VbRaddataDisplaying#3](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDisplaying/VB/PhoneNumberBox.vb#3)]  
  
3.  **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
## <a name="create-a-data-source-from-your-database"></a>データベースからデータ ソースを作成します。  
 この手順では、**データ ソース構成**ウィザードを使用して、Northwind サンプル データベースの `Customers` テーブルに基づいてデータ ソースを作成します。 接続を作成するには、Northwind サンプル データベースへのアクセス権を持っている必要があります。
  
#### <a name="to-create-the-data-source"></a>データ ソースを作成するには  
  
1.  **[データ]** メニューの **[データ ソースの表示]** をクリックします。  
  
2.  **[データ ソース]** ウィンドウで、**[新しいデータ ソースの追加]** をクリックして**データ ソース構成**ウィザードを起動します。  
  
3.  **[データソースの種類を選択]** ページで、**[データベース]** を選択し、**[次へ]** をクリックします。  
  
4.  **[データ接続の選択]** ページで、次のいずれかの操作を行います。  
  
    -   Northwind サンプル データベースへのデータ接続がドロップダウン リストに表示されている場合は選択します。  
  
    -   **[新しい接続]** を選択して **[接続の追加] または [接続の変更]** ダイアログ ボックスを表示します。  
  
5.  データベースにパスワードが必要な場合は、該当するオプションを選択して重要情報を含め、**[次へ]** をクリックします。  
  
6.  **[アプリケーション構成ファイルに接続文字列を保存]** ページで、**[次へ]** をクリックします。  
  
7.  **[データベース オブジェクトの選択]** ページで、**[テーブル]** ノードを展開します。  
  
8.  `Customers` テーブルを選択し、**[完了]** をクリックします。  
  
     プロジェクトに **NorthwindDataSet** が追加され、**[データ ソース]** ウィンドウに `Customers` テーブルが表示されます。  
  
## <a name="set-the-phone-column-to-use-the-phonenumberbox-control"></a>PhoneNumberBox コントロールを使用して、phone 列を設定します。  
 **[データ ソース]** ウィンドウでは、フォームにコントロールをドラッグする前に作成するコントロールを設定できます。  
  
#### <a name="to-set-the-phone-column-to-bind-to-the-phonenumberbox-control"></a>[Phone] 列を PhoneNumberBox コントロールにバインドするように設定するには  
  
1.  デザイナーで **Form1** を開きます。  
  
2.  **[データ ソース]** ウィンドウの **[Customers]** ノードを展開します。  
  
3.  **[Customers]** ノードのドロップダウン矢印をクリックし、コントロール リストの **[Details]** を選択します。  
  
4.  **[Phone]** 列のドロップダウン矢印をクリックし、**[Customize]** をクリックします。  
  
5.  **[データ UI カスタマイズ オプション]** ダイアログ ボックスの **[関連付けられたコントロール]** の一覧の **[PhoneNumberBox]** を選択します。  
  
6.  **[Phone]** 列のドロップダウン矢印をクリックし、**[PhoneNumberBox]** をクリックします。  
  
## <a name="addcontrols-to-the-form"></a>フォームに Addcontrols  
 **[データ ソース]** ウィンドウからフォームに項目をドラッグして、データ バインド コントロールを作成します。  
  
#### <a name="to-create-data-bound-controls-on-the-form"></a>フォームにデータ バインド コントロールを作成するには  
  
-   メインのドラッグ**顧客**ノードから、**データ ソース**ウィンドウから、フォームにことを確認します、`PhoneNumberBox`データを表示するコントロールを使用、`Phone`列。  
  
     説明のラベルが付いたデータ バインド コントロールとレコード間を移動するためのツール ストリップ (<xref:System.Windows.Forms.BindingNavigator>) がフォームに表示されます。 [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)、CustomersTableAdapter、<xref:System.Windows.Forms.BindingSource>、<xref:System.Windows.Forms.BindingNavigator> がコンポーネント トレイに表示されます。  
  
## <a name="run-the-application"></a>アプリケーションの実行  
  
#### <a name="to-run-the-application"></a>アプリケーションを実行するには  
  
-   F5 キーを押してアプリケーションを実行します。  
  
## <a name="next-steps"></a>次の手順  
 アプリケーションの要件に応じて、データ バインディングをサポートするコントロールの作成後に、追加の操作を実行できます。 次の手順として、一般的には、次のようなことを実行します。  
  
-   他のアプリケーションで再利用できるように、コントロール ライブラリにカスタム コントロールを配置します。  
  
-   より複雑なデータ バインディングのシナリオをサポートするコントロールを作成します。 詳細については、次を参照してください。[複合データ バインディングをサポートする Windows フォーム ユーザー コントロールを作成](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)と[ルックアップ データ バインディングをサポートする Windows フォーム ユーザー コントロール作成](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)です。  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio でのデータへの Windows フォーム コントロールのバインド](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [[データ ソース] ウィンドウからドラッグしたときに作成されるコントロールを設定する](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)
