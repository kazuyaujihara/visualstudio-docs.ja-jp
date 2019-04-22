---
title: 'チュートリアル: Windows フォームでの単純な WCF サービスの作成 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
helpviewer_keywords:
- WCF, walkthrough [Visual Studio]
- WCF, Visual Studio tools for
- WCF services
- WCF services, walkthrough
ms.assetid: 5fef1a64-27a4-4f10-aa57-29023e28a2d6
caps.latest.revision: 29
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c2c5fba8914ba3b5404412c0cbc55af36fe15c21
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59661040"
---
# <a name="walkthrough-creating-a-simple-wcf-service-in-windows-forms"></a>チュートリアル: Windows フォームでのシンプルな WCF サービスの作成
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このチュートリアルは、単純な [!INCLUDE[vsindigo](../includes/vsindigo-md.md)] サービスを作成し、テストして、Windows フォーム アプリケーションからアクセスする方法を例示しています。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="creating-the-service"></a>サービスの作成  
  
#### <a name="to-create-a-wcf-service"></a>WCF サービスを作成するには  
  
1.  **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。  
  
2.  **[新しいプロジェクト]** ダイアログ ボックスで、**[Visual Basic]** または **[Visual C#]** ノードを展開し、**[WCF]** をクリックしてから **[WCF サービス ライブラリ]** をクリックします。 **[OK]** をクリックして、プロジェクトを開きます。  
  
     ![WCF サービス ライブラリ プロジェクト](../data-tools/media/wcf1.PNG "wcf1")  
  
    > [!NOTE]
    >  これにより、テストしてアクセスすることが可能な機能するサービスが作成されます。 次の 2 つの手順は、別のデータ型を使用するように既定の方法を変更する方法を示しています。 実際のアプリケーションで、独自の関数をサービスに追加することもできます。  
  
3.  ![IService1 ファイル](../data-tools/media/wcf2.png "wcf2")  
  
     **ソリューション エクスプ ローラー**、IService1.vb または IService1.cs をダブルクリックし、次の行を探します。  
  
     [! コード csharp [WCFWalkthrough 4] (../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/iservice1 (2).cs 4)] [! コード vb [WCFWalkthrough 4] (../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/iservice1 (2).vb 4)]  
  
     `value` パラメーターの種類を `String` に変更します。  
  
     [!code-csharp[WCFWalkthrough#1](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/iservice1.cs#1)]
     [!code-vb[WCFWalkthrough#1](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/iservice1.vb#1)]  
  
     上記のコードで、`<OperationContract()>` または `[OperationContract]` 属性に注意してください。 これらの属性は、サービスによって公開されている任意のメソッドに必要です。  
  
4.  ![Service1 ファイル](../data-tools/media/wcf3.png "wcf3")  
  
     **ソリューション エクスプ ローラー**、Service1.vb または Service1.cs をダブルクリックし、次の行を探します。  
  
     [! コード csharp [WCFWalkthrough 5] (../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/service1 (2).cs 5)] [! コード vb [WCFWalkthrough 5] (../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/service1 (2).vb 5)]  
  
     値パラメーターの種類を `String` に変更します。  
  
     [!code-csharp[WCFWalkthrough#2](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/service1.cs#2)]
     [!code-vb[WCFWalkthrough#2](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/service1.vb#2)]  
  
## <a name="testing-the-service"></a>サービスのテスト  
  
#### <a name="to-test-a-wcf-service"></a>WCF サービスをテストするには  
  
1.  **F5** キーを押してサービスを実行します。 A **WCF テスト クライアント**フォームが表示され、サービスが読み込まれます。  
  
2.  **[WCF のテスト用クライアント]** フォームで、**IService1** の下の **GetData()** メソッドをダブルクリックします。 **GetData**タブが表示されます。  
  
     ![GetData&#40; &#41;メソッド](../data-tools/media/wcf4.png "wcf4")  
  
3.  **[要求]** ボックスで、**[値]** フィールドを選択して「`Hello`」と入力します。  
  
     ![[値] フィールド](../data-tools/media/wcf5.png "wcf5")  
  
4.  **[起動]** ボタンをクリックします。 場合、**セキュリティ警告** ダイアログ ボックスが表示されたら、をクリックして**OK**します。 結果が表示されます、**応答**ボックス。  
  
     ![応答 ボックスに結果](../data-tools/media/wcf6.png "wcf6")  
  
5.  **[ファイル]** メニューの **[終了]** をクリックして、テスト フォームを閉じます。  
  
## <a name="accessing-the-service"></a>サービスへのアクセス  
  
#### <a name="to-reference-a-wcf-service"></a>WCF サービスを参照するには  
  
1.  **[ファイル]** メニューの **[追加]** をポイントし、**[新しいプロジェクト]** をクリックします。  
  
2.  **新しいプロジェクト**] ダイアログ ボックスで、展開、 **Visual Basic**または**Visual c#** ノード**Windows**、し、[ **Windows フォーム アプリケーション**します。 **[OK]** をクリックして、プロジェクトを開きます。  
  
     ![Windows フォーム アプリケーション プロジェクト](../data-tools/media/wcf7.png "wcf7")  
  
3.  **[WindowsApplication1]** を右クリックして **[サービス参照の追加]** をクリックします。 **サービス参照の追加** ダイアログ ボックスが表示されます。  
  
4.  **[サービス参照の追加]** ダイアログ ボックスで **[探索]** をクリックします。  
  
     ![サービス参照の追加 ダイアログ ボックス](../data-tools/media/wcf8.png "wcf8")  
  
     **Service1**に表示される、**サービス**ウィンドウ。  
  
5.  **[OK]** をクリックしてサービス参照を追加します。  
  
#### <a name="to-build-a-client-application"></a>クライアント アプリケーションをビルドするには  
  
1.  **ソリューション エクスプローラー**で、**[Form1.vb]** または **[Form1.cs]** をダブルクリックして、Windows フォーム デザイナーを (まだ開いていない場合に) 開きます。  
  
2.  **ツールボックス**で、`TextBox` コントロール、`Label` コントロール、および `Button` コントロールをフォームにドラッグします。  
  
     ![フォームにコントロールを追加する](../data-tools/media/wcf9.png "wcf9")  
  
3.  `Button` をダブルクリックし、`Click` イベント ハンドラーに次のコードを追加します。  
  
     [!code-csharp[WCFWalkthrough#3](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/form1.cs#3)]
     [!code-vb[WCFWalkthrough#3](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/form1.vb#3)]  
  
4.  **ソリューション エクスプローラー**で、**[WindowsApplication1]** を右クリックして **[スタートアップ プロジェクトに設定]** をクリックします。  
  
5.  **F5** キーを押してプロジェクトを実行します。 いくつかのテキストを入力し、ボタンをクリックします。 ラベルに「You entered:」と入力したテキストが表示されます。  
  
     ![結果を表示するフォーム](../data-tools/media/wcf10.png "wcf10")  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio での Windows Communication Foundation サービスと WCF データ サービス](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)
