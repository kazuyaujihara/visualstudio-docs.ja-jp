---
title: Visual Studio の Visual Basic の概要
description: Visual Studio で Visual Basic コンソール アプリを作成する方法の詳細な手順を説明します。
ms.custom: ''
ms.date: 08/10/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: tutorial
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: 5b3288bc83e3cbeef9b46be2b3c6c7e17874d20f
ms.sourcegitcommit: db94ca7a621879f98d4c6aeefd5e27da1091a742
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2018
ms.locfileid: "42626902"
---
# <a name="tutorial-get-started-with-visual-basic-in-visual-studio"></a>チュートリアル: Visual Studio の Visual Basic の概要

この Visual Basic (VB) に関するチュートリアルでは、Visual Studio を使用して、いくつかの異なるコンソール アプリを作成して実行しながら、[Visual Studio の統合開発環境 (IDE)](visual-studio-ide.md) の一部の機能を検討します。

Visual Studio をまだインストールしていない場合は、[Visual Studio のダウンロード](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ページに移動し、無料試用版をインストールしてください。

## <a name="create-a-project"></a>プロジェクトを作成する

まず、Visual Basic アプリケーション プロジェクトを作成します。 このプロジェクトの種類には、必要となるすべてのテンプレート ファイルが付属していますので、何も追加する必要はありません。

1. Visual Studio 2017 を開きます。

2. 上部のメニュー バーで、**[ファイル]** > **[新規作成]** > **[プロジェクト]** の順に選択します。

3. **[新しいプロジェクト]** ダイアログ ボックスの左側のウィンドウで、**[Visual Basic]** を展開し、**[.NET Core]** を選択します。 中央のウィンドウで、**[Console App (.NET Core)]** を選択します。 次に、ファイルに *HelloWorld* という名前を付けます。

   ![Visual Studio IDE の [新しいプロジェクト] ダイアログ ボックスに示されているコンソール アプリ (.NET Core) プロジェクト テンプレート](../ide/media/new-project-vb-dotnetcore-whatisyourname-console-app.png)

### <a name="add-a-workgroup-optional"></a>ワークグループを追加する (省略可能)

**コンソール アプリ (.NET Core)** プロジェクト テンプレートが表示されない場合は、**.NET Core クロスプラットフォームの開発**ワークロードを追加して取得できます。 コンピューターにインストールされている Visual Studio 2017 の更新プログラムに応じて、次の 2 つの方法のうちのいずれかでこのワークロードを追加することができます。

#### <a name="option-1-use-the-new-project-dialog-box"></a>オプション 1: [新しいプロジェクト] ダイアログ ボックスを使用する

1. **[新しいプロジェクト]** ダイアログ ボックスの左側のウィンドウで、**[Visual Studio インストーラーを開く]** リンクをクリックします。

   ![[新しいプロジェクト] ダイアログ ボックスで [Visual Studio インストーラーを開く] リンクをクリックする](../ide/media/vs-open-visual-studio-installer-generic.png)

1. Visual Studio インストーラーが起動します。 **[.NET Core クロスプラットフォームの開発]** ワークロードを選択し、**[変更]** を選択します。

   ![Visual Studio インストーラーの [.NET Core クロスプラットフォームの開発] ワークロード](../ide/media/quickstart-aspnet-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>オプション 2: [ツール] メニュー バーを使用する

1. **[新しいプロジェクト]** ダイアログ ボックスを取り消し、上部のメニュー バーから **[ツール]** > **[ツールと機能を取得]** の順に選択します。

1. Visual Studio インストーラーが起動します。 **[.NET Core クロスプラットフォームの開発]** ワークロードを選択し、**[変更]** を選択します。

## <a name="create-a-what-is-your-name-application"></a>"What Is Your Name" アプリケーションを作成する

名前の入力を求めた後に、日付と時刻と共にそれを表示するアプリを作成してみましょう。 次の手順に従います。

1. *WhatIsYourName* プロジェクトがまだ開いていない場合は、これを開きます。

1. 次の Visual Basic コードを `Sub Main(args As String())` 行と `End Sub` 行の間に入力します。このコードは左かっこのすぐ後に配置します。

     ```vb
     Console.WriteLine(vbCrLf + "What is your name? ")
     Dim name = Console.ReadLine()
     Dim currentDate = DateTime.Now
     Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}")
     Console.Write(vbCrLf + "Press any key to exit... ")
     Console.ReadKey(True)
    ```

    このコードでは、既存の <xref:System.Console.WriteLine%2A>、<xref:System.Console.Write%2A>、および <xref:System.Console.ReadKey%2A> ステートメントを置き換えます。

   ![What Is Your Name コードが表示されているコード ウィンドウ](../ide/media/vb-codewindow-what-name.png)

1. コンソール ウィンドウが開いたら、自分の名前を入力します。 コンソール ウィンドウは次のスクリーン ショットのようになります。

   ![What Is Your Name、時刻と日付、Press any key to continue メッセージが表示されているコンソール ウィンドウ](../ide/media/vb-console-what-name.png)

1. 任意のキーを押して、コンソール ウィンドウを閉じます。

## <a name="create-a-calculate-this-application"></a>"Calculate This" アプリケーションを作成する

1. Visual Studio 2017 を開き、上部のメニュー バーから **[ファイル]** > **[新規作成]** > **[プロジェクト]** の順に選択します。

1. **[新しいプロジェクト]** ダイアログ ボックスの左側のウィンドウで、**[Visual Basic]** を展開し、**[.NET Core]** を選択します。 中央のウィンドウで、**[Console App (.NET Core)]** を選択します。 次に、ファイルに *CalculateThis* という名前を付けます。

1. `Module Program` 行と `End Module` 行の間に次のコードを入力します。

   ```vb
   Public num1 As Integer
   Public num2 As Integer
   Public answer As Integer
   Sub Main()
       Console.WriteLine("Type a number and press Enter")
       num1 = Console.ReadLine()
       Console.WriteLine("Type another number to add to it and press Enter")
       num2 = Console.ReadLine()
       answer = num1 + num2
       Console.WriteLine("The answer is " & answer)
       Console.ReadLine()
   End Sub
   ```

   コード ウィンドウは次のスクリーンショットのようになります。

   ![Calculate This コードが表示されているコード ウィンドウ](../ide/media/vb-codewindow-calculate-this.png)

1. **CalculateThis** をクリックしてプログラムを実行します。 コンソール ウィンドウは次のスクリーン ショットのようになります。

    ![実行するアクションに対するプロンプトを含む、CaluculateThis アプリが表示されているコンソール ウィンドウ](../ide/media/vb-console-calculate-this.png)

## <a name="quick-answers-faq"></a>FAQ に対する簡単な回答

以下の簡単な FAQ で、主な概念をいくつか示します。

### <a name="what-is-visual-basic"></a>Visual Basic とは何ですか?

Visual Basic は、習得しやすいように設計されたタイプ セーフのプログラミング言語です。 BASIC (つまり、初心者向けの汎用シンボリック命令コード) から派生したものです。

### <a name="what-is-visual-studio"></a>Visual Studio とは何ですか?

Visual Studio は、開発者向け生産性向上ツールの統合開発スイートです。 プログラムやアプリケーションを作成するために使用できるプログラムのようなものと考えてください。

### <a name="what-is-a-console-app"></a>コンソール アプリとは何ですか?

コンソール アプリは、コマンドライン ウィンドウ (コンソールともいう) で入力を取得して、 出力を表示します。

### <a name="what-is-net-core"></a>.NET Core とは何ですか?

.NET Core は、.NET Framework の次の進化段階です。 .NET Framework ではプログラミング言語間でコードを共有できましたが、.NET Core ではプラットフォーム間でコードを共有する機能が追加されました。 さらに良い点は、オープン ソースであるという点です  (.NET Framework および .NET Core の両方にビルド済みの機能のライブラリと、コードを実行する仮想マシンとして機能する、共通言語ランタイム (CLR) が含まれています)。

## <a name="next-steps"></a>次の手順

これでこのチュートリアルは完了です。 詳細については、以下のチュートリアルをご覧ください。

> [!div class="nextstepaction"]
> [ビデオ チュートリアル: 初めて使用される方向けの Visual Basic の基本](https://mva.microsoft.com/en-us/training-courses/visual-basic-fundamentals-for-absolute-beginners-16507)

## <a name="see-also"></a>関連項目

* [Visual Basic の新機能](/dotnet/visual-basic/getting-started/whats-new)
* [Visual Basic コード ファイルの IntelliSense](visual-basic-specific-intellisense.md)
* [Visual Basic の言語リファレンス](/dotnet/visual-basic/language-reference/index)