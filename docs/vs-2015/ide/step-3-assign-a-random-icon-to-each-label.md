---
title: '手順 3: 各ラベルへのランダムなアイコンの割り当て |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 0ba5ed7a-9aaa-41f4-95d2-e3c2d567bc79
caps.latest.revision: 33
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3562b74939fe9207ddcf10e98bd0b4d0d7d1bead
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60085988"
---
# <a name="step-3-assign-a-random-icon-to-each-label"></a>手順 3: 各ラベルにランダムなアイコンを割り当てる
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ゲームで毎回、同じアイコンが同じセルに表示されていたのでは、やりがいがありません。 これを避けるには、`AssignIconsToSquares()` メソッドを使用して、フォームのラベル コントロールにアイコンをランダムに割り当てます。  
  
### <a name="to-assign-a-random-icon-to-each-label"></a>各ラベルにランダムなアイコンを割り当てるには  
  
1. 次のコードを追加する前に、メソッドのしくみについて検討します。 新しいキーワード `foreach` (Visual C# の場合) および `For Each` (Visual Basic の場合) があります  (1 つの行は意図的にコメント アウトされています。これについてはこの手順の最後に説明します)。  
  
     [!code-csharp[VbExpressTutorial4Step2_3_4#2](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step2_3_4/cs/form1.cs#2)]
     [!code-vb[VbExpressTutorial4Step2_3_4#2](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step2_3_4/vb/form1.vb#2)]  
  
2. 前の手順で示されているように、`AssignIconsToSquares()` メソッドを追加します。 このメソッドを、「[手順 2:Random オブジェクトおよびアイコンの一覧に追加](../ide/step-2-add-a-random-object-and-a-list-of-icons.md)します。  
  
     前に説明したように、`AssignIconsToSquares()` メソッドに新しいものが含まれています。つまり、`foreach` ループ (Visual C# の場合) および `For Each` (Visual Basic の場合) です。 `For Each` ループは、同じ処理を繰り返し実行する必要がある場合にいつでも使用できます。 ここでは、次のコードで説明されているように、TableLayoutPanel のラベルごとに同じステートメントを実行する必要があります。 最初の行では、`control` という名前の変数を作成し、その変数に一度に 1 つずつコントロールを格納して、そのコントロールに対してループ内のステートメントを実行します。  
  
     [!code-csharp[VbExpressTutorial4Step2_3_4#14](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step2_3_4/cs/form1.cs#14)]
     [!code-vb[VbExpressTutorial4Step2_3_4#14](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step2_3_4/vb/form1.vb#14)]  
  
    > [!NOTE]
    >  "iconLabel" および "control" という名前が使用されているのは、わかりやすくするためです。 これらの名前を任意の名前に置き換えても、コードはまったく同じように動作します (ただしループ内の各ステートメントで名前を変更する必要はあります)。  
  
     `AssignIconsToSquares()` メソッドは、TableLayoutPanel の各ラベル コントロールを反復処理し、それぞれに対し同じステートメントを実行します。 これらのステートメントは、「[手順 2:Random オブジェクトおよびアイコンの一覧に追加](../ide/step-2-add-a-random-object-and-a-list-of-icons.md)します。 (リストに各アイコンを 2 つずつ含め、ランダムなラベル コントロールにアイコンのペアが割り当てられるようにしたのはこのためです)。  
  
     `foreach` または `For Each` ループ内で実行されるコードを詳しく見てみましょう。 次に示しているのは前に示したコードの一部です。  
  
     [!code-csharp[VbExpressTutorial4Step2_3_4#16](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step2_3_4/cs/form1.cs#16)]
     [!code-vb[VbExpressTutorial4Step2_3_4#16](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step2_3_4/vb/form1.vb#16)]  
  
     最初の行では、`control` 変数を `iconLabel` という名前のラベルに変換しています。 その次の行は、変換が成功したかどうかを確認する `if` ステートメントです。 変換が成功した場合は、`if` ステートメント内のステートメントが実行されます  (前のチュートリアルでも説明したように、`if` ステートメントは、指定した任意の条件を評価するために使用されます)。`if` ステートメントの最初の行では、`randomNumber` という名前の変数を作成し、icons リスト内の項目のいずれかに対応する乱数をこの変数に格納します。 そのために、前に作成した `Next` オブジェクトの `Random` メソッドを使用します。 `Next` メソッドは乱数を返します。 またこの行では、`Count` リストの `icons` プロパティを使用して、乱数を選択する範囲を決定しています。 次の行では、icons リストのいずれかの項目をラベルの `Text` プロパティに割り当てています。 コメントアウトしている行は、このトピックの後半で説明します。 最後に、`if` ステートメントの最終の行で、フォームに追加したアイコンをリストから削除しています。  
  
     コード内にわからない部分があれば、コード要素の上にマウス ポインターを合わせると、関連するヒントが表示されます。 Visual Studio デバッガーを使用して、プログラムの実行中にコードの各行をステップ実行することもできます。 参照してください[How Do i:Visual Studio のデバッガーでステップでしょうか。](http://msdn.microsoft.com/vstudio/ee672313.aspx)または[デバッガーでコード間の移動](../debugger/navigating-through-code-with-the-debugger.md)詳細についてはします。  
  
3. ゲーム ボードをアイコンで埋めるには、プログラムが起動したらすぐに `AssignIconsToSquares()` メソッドを呼び出す必要があります。 Visual C# を使用している場合は、`Form1`*constructor* の `InitializeComponent()` メソッドの呼び出しのすぐ下にステートメントを追加し、フォームが新しいメソッドを呼び出してフォーム自体の設定後に表示されるようにします。 新しいオブジェクト (クラスや構造体など) を作成するときは、コンストラクターを呼び出します。 詳細については、「[コンストラクター (C# プログラミング ガイド)](http://msdn.microsoft.com/library/ace5hbzh.aspx)」または「[コンストラクタとデストラクターの使用方法](http://msdn.microsoft.com/library/2z08e49e%28v=vs.90%29.aspx)」 (Visual Basic の場合) を参照してください。  
  
     [!code-csharp[VbExpressTutorial4Step2_3_4#13](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step2_3_4/cs/form1.cs#13)]  
  
     Visual Basic の場合は、`AssignIconsToSquares()` メソッドの呼び出しを `Form1_Load` メソッドに追加します。コードは次のようになります。  
  
    ```vb  
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
        AssignIconsToSquares()  
    End Sub  
    ```  
  
4. プログラムを保存し、実行します。 各ラベルに割り当てられたランダムなアイコンを備えたフォームが表示されます。  
  
5. いったんプログラムを終了して、再び実行します。 次の図に示すように、各ラベルに別のアイコンが割り当てられています。  
  
     ![ランダムなアイコンが表示された絵合わせゲーム](../ide/media/express-tut4step3.png "Express_Tut4Step3")  
ランダムなアイコンが表示された絵合わせゲーム  
  
     アイコンは、まだ非表示に設定されていないため、表示されています。 アイコンをプレーヤーに非表示にするには、各ラベルの `Forecolor` プロパティをその `BackColor` プロパティと同じ色に設定できます。  
  
    > [!TIP]
    >  ラベルのようなコントロールを非表示にする別の方法は、**Visible** プロパティを `False` に設定することです。  
  
6. アイコンを非表示にするには、プログラムを停止し、`For Each` ループ内のコードのコメント行からコメント記号を削除します。  
  
     [!code-csharp[VbExpressTutorial4Step2_3_4#15](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step2_3_4/cs/form1.cs#15)]
     [!code-vb[VbExpressTutorial4Step2_3_4#15](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step2_3_4/vb/form1.vb#15)]  
  
7. メニュー バーで、**[すべて保存]** をクリックし、プログラムを保存したうえで実行します。 アイコンが非表示になったように見えます。青い背景のみが表示されます。 ただし、アイコンはランダムに割り当てられて、そこに存在しています。 アイコンは、背景と同じ色であるため、プレーヤーには見えなくなっています。 これで、ゲームはやりがいのあるものになりました。プレーヤーはすべてのアイコンをすぐに見ることができなくなったためです。  
  
### <a name="to-continue-or-review"></a>続行または確認するには  
  
- チュートリアルの次の手順に進むには、「[手順 4:各ラベルに Click イベント ハンドラーを追加](../ide/step-4-add-a-click-event-handler-to-each-label.md)します。  
  
- チュートリアルの前の手順に戻るには、「[手順 2:Random オブジェクトおよびアイコンの一覧に追加](../ide/step-2-add-a-random-object-and-a-list-of-icons.md)します。
