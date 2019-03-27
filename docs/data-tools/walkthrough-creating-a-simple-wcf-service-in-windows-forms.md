---
title: 'チュートリアル: Windows フォームでの簡単な WCF サービスの作成'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WCF, walkthrough [Visual Studio]
- WCF, Visual Studio tools for
- WCF services
- WCF services, walkthrough
ms.assetid: 5fef1a64-27a4-4f10-aa57-29023e28a2d6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 97bbf8212caf87f28849df15d350811579f22ccd
ms.sourcegitcommit: 3d37c2460584f6c61769be70ef29c1a67397cf14
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "58325229"
---
# <a name="walkthrough-create-a-simple-wcf-service-in-windows-forms"></a>チュートリアル: Windows フォームにおける単純な WCF サービスを作成します。

このチュートリアルでは、単純な Windows Communication Foundation (WCF) サービスを作成、テスト、および Windows フォーム アプリケーションからアクセスする方法を示します。

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="create-a-service"></a>サービスを作成する

1. Visual Studio を開きます。

::: moniker range="vs-2017"

2. **[ファイル]** メニューで、 **[新規]** > **[プロジェクト]** をクリックします。

3. **新しいプロジェクト** ダイアログ ボックスで、展開、 **Visual Basic**または**Visual C#** ノード選択**WCF**と、その後**WCF サービス ライブラリ**します。

4. **[OK]** をクリックして、プロジェクトを作成します。

   ![WCF サービス ライブラリ プロジェクト](../data-tools/media/wcf1.png)

::: moniker-end

::: moniker range=">=vs-2019"

2. スタート ウィンドウで、**[新しいプロジェクトの作成]** を選択します。

3. 型**wcf サービス ライブラリ**で検索ボックスに、**新しいプロジェクトを作成**ページ。 いずれかを選択、C#または Visual Basic テンプレートを**WCF サービス ライブラリ**、順にクリックします**次**します。

   ![Visual Studio 2019 で新しい WCF サービス ライブラリ プロジェクトを作成します。](media/vs-2019/create-new-wcf-service-library.png)

   > [!TIP]
   > テンプレートが表示されない場合は、インストールする必要があります、 **Windows Communication Foundation** Visual Studio のコンポーネント。 選択**他のツールと機能をインストール**を Visual Studio インストーラーを開きます。 選択、**個々 のコンポーネント**] タブで、下へスクロールして**開発アクティビティ**、し、[ **Windows Communication Foundation**します。 **[変更]** をクリックします。

4. **新しいプロジェクトを構成する**] ページで [**作成**です。

::: moniker-end

   > [!NOTE]
   > これにより、テストしてアクセスすることが可能な機能するサービスが作成されます。 次の 2 つの手順は、別のデータ型を使用するように既定の方法を変更する方法を示しています。 実際のアプリケーションで、独自の関数をサービスに追加することもできます。

5. **ソリューション エクスプ ローラー**、ダブルクリックして**IService1.vb**または**IService1.cs**します。

   ![IService1 ファイル](../data-tools/media/wcf2.png)

   次の行を見つけます。

   [!code-csharp[WCFWalkthrough#4](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.cs)]
   [!code-vb[WCFWalkthrough#4](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.vb)]

   種類を変更、`value`文字列へのパラメーター。

   [!code-csharp[WCFWalkthrough#1](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.cs)]
   [!code-vb[WCFWalkthrough#1](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.vb)]

   上記のコードで、`<OperationContract()>` または `[OperationContract]` 属性に注意してください。 これらの属性は、サービスによって公開されている任意のメソッドに必要です。

6. **ソリューション エクスプ ローラー**、ダブルクリックして**Service1.vb**または**Service1.cs**します。

   ![Service1 ファイル](../data-tools/media/wcf3.png)

   次の行を見つけます。

   [!code-vb[WCFWalkthrough#5](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.vb)]
   [!code-csharp[WCFWalkthrough#5](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.cs)]

   種類を変更、`value`文字列へのパラメーター。

   [!code-csharp[WCFWalkthrough#2](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.cs)]
   [!code-vb[WCFWalkthrough#2](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.vb)]

## <a name="test-the-service"></a>サービスをテストする

1. **F5** キーを押してサービスを実行します。 A **WCF テスト クライアント**フォームが表示され、サービスを読み込みます。

2. **[WCF のテスト用クライアント]** フォームで、**IService1** の下の **GetData()** メソッドをダブルクリックします。 **GetData**タブが表示されます。

     ![GetData&#40; &#41;メソッド](../data-tools/media/wcf4.png)

3. **[要求]** ボックスで、**[値]** フィールドを選択して「`Hello`」と入力します。

     ![[値] フィールド](../data-tools/media/wcf5.png)

4. **[起動]** ボタンをクリックします。 場合、**セキュリティ警告** ダイアログ ボックスが表示されたら、をクリックして**OK**します。 結果が表示されます、**応答**ボックス。

     ![[応答] ボックスに結果が表示される](../data-tools/media/wcf6.png)

5. **[ファイル]** メニューの **[終了]** をクリックして、テスト フォームを閉じます。

## <a name="access-the-service"></a>サービスへのアクセスします。

### <a name="reference-the-wcf-service"></a>WCF サービスを参照します。

1. **[ファイル]** メニューの **[追加]** をポイントし、**[新しいプロジェクト]** をクリックします。

2. **新しいプロジェクト** ダイアログ ボックスで、展開、 **Visual Basic**または**Visual c#** ノードの  **Windows**、し、 **Windows フォーム アプリケーション**します。 **[OK]** をクリックして、プロジェクトを開きます。

     ![Windows フォーム アプリケーション プロジェクト](../data-tools/media/wcf7.png)

3. **[WindowsApplication1]** を右クリックして **[サービス参照の追加]** をクリックします。 **サービス参照の追加** ダイアログ ボックスが表示されます。

4. **[サービス参照の追加]** ダイアログ ボックスで **[探索]** をクリックします。

     ![[サービス参照の追加] ダイアログ ボックス](../data-tools/media/wcf8.png)

     **Service1**で表示されます、**サービス**ウィンドウ。

5. **[OK]** をクリックしてサービス参照を追加します。

### <a name="build-a-client-application"></a>クライアント アプリケーションを構築します

1. **ソリューション エクスプローラー**で、**[Form1.vb]** または **[Form1.cs]** をダブルクリックして、Windows フォーム デザイナーを (まだ開いていない場合に) 開きます。

2. **ツールボックス**で、`TextBox` コントロール、`Label` コントロール、および `Button` コントロールをフォームにドラッグします。

     ![フォームへのコントロールの追加](../data-tools/media/wcf9.png)

3. `Button` をダブルクリックし、`Click` イベント ハンドラーに次のコードを追加します。

     [!code-csharp[WCFWalkthrough#3](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.cs)]
     [!code-vb[WCFWalkthrough#3](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.vb)]

4. **ソリューション エクスプローラー**で、**[WindowsApplication1]** を右クリックして **[スタートアップ プロジェクトに設定]** をクリックします。

5. **F5** キーを押してプロジェクトを実行します。 いくつかのテキストを入力し、ボタンをクリックします。 ラベルが表示されます"入力した:"と入力したテキストを表示します。

     ![結果を表示するフォーム](../data-tools/media/wcf10.png)

## <a name="see-also"></a>関連項目

- [Visual Studio での Windows Communication Foundation サービスと WCF データ サービス](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)