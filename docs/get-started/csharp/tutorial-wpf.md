---
title: C# で WPF を使った Hello World アプリ
description: Windows Presentation Foundation (WPF) UI フレームワークを使って、Visual Studio で 単純な Windows デスクトップ .NET アプリを C# で作成します。
ms.custom: seodec18, get-started
ms.date: 08/09/2019
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.topic: conceptual
dev_langs:
- CSharp
ms.assetid: f84339c7-d617-4f56-bfcd-af2215c347ba
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: d146416190924c8f1835ef17bc0fb622fcc53e03
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "70180218"
---
# <a name="tutorial-create-a-simple-application-with-c"></a>チュートリアル: C\# で単純なアプリケーションを作成する

このチュートリアルを完了すると、Visual Studio を使用してアプリケーションを開発する際に使用できるさまざまなツール、ダイアログ ボックス、およびデザイナーの使用方法を習得できます。 "Hello, World" アプリケーションの作成、UI の設計、コードの追加、エラーのデバッグを行いながら、統合開発環境 ([IDE](visual-studio-ide.md)) での作業方法について学習します。

::: moniker range="vs-2017"
Visual Studio をまだインストールしていない場合は、[Visual Studio のダウンロード](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) ページに移動し、無料試用版をインストールしてください。
::: moniker-end
::: moniker range=">=vs-2019"
Visual Studio をまだインストールしていない場合は、[Visual Studio のダウンロード](https://visualstudio.microsoft.com/downloads) ページに移動し、無料試用版をインストールしてください。
::: moniker-end

## <a name="configure-the-ide"></a>IDE の構成

::: moniker range="vs-2017"

Visual Studio を初めて開くときには、サインインが求められます。 このチュートリアルでは、この手順は任意です。 次に、開発設定と色テーマの選択を求めるダイアログ ボックスが表示される場合があります。 既定値のままにして **[Visual Studio の開始]** を選択します。

![設定の選択ダイアログ ボックス](../media/exploreide-settings.png)

Visual Studio を起動すると、ツール ウィンドウ、メニューとツール バー、メイン ウィンドウ領域が表示されます。 ツール ウィンドウは、アプリケーション ウィンドウの左側および右側にドッキングされており、上部には **クイック起動**、メニュー バー、および標準ツール バーがあります。 アプリケーション ウィンドウの中央には、 **スタート ページ**が表示されます。 ソリューションかプロジェクトが読み込まれると、 **[スタート ページ]** がある領域にエディターとデザイナーが表示されます。 アプリケーションを開発する場合は、ほとんどの時間をこの中央の領域での作業に費やします。

![全般設定が適用された Visual Studio 2017 IDE](../media/exploreide-idewithgeneralsettings.png "全般設定が適用された Visual Studio 2017 IDE のスクリーンショット")

::: moniker-end

::: moniker range=">=vs-2019"

Visual Studio を起動するときに、スタート ウィンドウが最初に表示されます。 **[コードなしで続行]** を選択して、開発環境を開きます。 ツール ウィンドウ、メニューとツール バー、メイン ウィンドウ領域が表示されます。 ツール ウィンドウは、アプリケーション ウィンドウの左側と右側にドッキングされており、上部には検索ボックス、メニュー バー、標準のツール バーがあります。 ソリューションまたはプロジェクトを読み込むと、アプリケーション ウィンドウの中央スペースにエディターとデザイナーが表示されます。 アプリケーションを開発する場合は、ほとんどの時間をこの中央の領域での作業に費やします。

::: moniker-end

## <a name="create-the-project"></a>プロジェクトの作成

Visual Studio でアプリケーションを作成するには、最初にプロジェクトおよびソリューションを作成します。 この例では、Windows Presentation Foundation (WPF) プロジェクトを作成します。

::: moniker range="vs-2017"

1. 新しいプロジェクトを作成します。 メニュー バーで **[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** を選択します。

     ![メニュー バーで、[ファイル]、[新規作成]、[プロジェクト] の順に選択する](../media/exploreide-filenewproject.png "[ファイル]、[新規作成]、[プロジェクト] が選択されたメニュー バーのスクリーンショット")

1. **[新しいプロジェクト]** ダイアログで、 **[インストール済み]**  >  **[Visual C#]**  >  **[Windows デスクトップ]** カテゴリを選択し、 **[WPF アプリ (.NET Framework)]** テンプレートを選択します。 プロジェクトに **HelloWPFApp** という名前を付けて、 **[OK]** を選択します。

     ![Visual Studio の [新しいプロジェクト] ダイアログの WPF アプリ テンプレート](media/exploreide-newprojectcsharp.png "Visual Studio の [新しいプロジェクト] ダイアログの WPF アプリ テンプレートのスクリーンショット")

::: moniker-end

::: moniker range="vs-2019"

1. Visual Studio 2019 を開きます。

1. スタート ウィンドウで、 **[新しいプロジェクトの作成]** を選択します。

   ![[新しいプロジェクトの作成] ウィンドウを表示する](../../get-started/media/vs-2019/start-window-create-new-project.png "[新しいプロジェクトの作成] ウィンドウのスクリーンショット")

1. **[新しいプロジェクトの作成]** 画面で、"WPF" を検索し、 **[WPF アプリ (.NET Framework)]** を選択してから、 **[次へ]** を選択します。

   ![[新しいプロジェクトの作成] ダイアログの WPF アプリ テンプレート](media/vs-2019/exploreide-newprojectcsharp-vs2019.png "[新しいプロジェクトの作成] ダイアログの WPF アプリ テンプレートのスクリーンショット")

1. 次の画面で、プロジェクトに **HelloWPFApp** という名前を付けて、 **[作成]** を選択します。

   ![プロジェクトに "HelloWPFApp" という名前を付ける](./media/vs-2019/exploreide-nameproject.png "プロジェクトに名前を付けるウィンドウのスクリーンショット")

::: moniker-end

Visual Studio は HelloWPFApp というプロジェクトとソリューションを作成し、**ソリューション エクスプローラー**は各種ファイルを表示します。 **WPF デザイナー**には、*MainWindow.xaml* のデザイン ビューと XAML ビューが分割ビューで表示されます。 分割線をスライドして、それぞれのビューの表示範囲を増減できます。 ビジュアル ビューか XAML ビューの一方のみを表示することも選択できます。

![IDE の WPF プロジェクトとソリューション](media/exploreide-wpfproject-cs.png "IDE の WPF プロジェクトとソリューションのスクリーンショット")

> [!NOTE]
> XAML (eXtensible Application Markup Language) について詳しくは、[WPF のための XAML の概要](/dotnet/framework/wpf/advanced/xaml-overview-wpf)に関するページをご覧ください。

プロジェクトは、作成後にカスタマイズできます。 これを行うには、 **[表示]** メニューの **[プロパティ ウィンドウ]** を選択するか、または **F4** キーを押します。 これで、アプリケーションのプロジェクト項目やコントロールなどの項目のオプションを表示および変更できます。

   ![プロパティ ウィンドウ](../media/exploreide-hellowpfappfiles.png "プロパティ ウィンドウと WPF ファイル アプリ名のスクリーンショット")   

### <a name="change-the-name-of-mainwindowxaml"></a>MainWindow.xaml の名前を変更する

それでは、MainWindow に具体的な名前を付けましょう。

1. **ソリューション エクスプローラー**で、*MainWindow.xaml* を選択します。 **[プロパティ]** ウィンドウが表示されるはずですが、表示されない場合は、 **[表示]** メニューを選択し、 **[プロパティ ウィンドウ]** 項目を選択します。 (または、**F4** キーを押します。)

1. **[File Name]** プロパティを `Greetings.xaml`に変更します。

     ![ファイル名が強調表示されたプロパティ ウィンドウ](../media/exploreide-filenameinpropertieswindow.png "ファイル名が強調表示されたプロパティ ウィンドウのスクリーンショット")

     **ソリューション エクスプローラー**に表示されているこのファイルの名前が *Greetings.xaml* になり、入れ子になっているコード ファイルの名前が *Greetings.xaml.cs* になります。 このコード ファイルは、 *.xaml* ファイル ノードの下に入れ子になっており、相互に密接に関連していることが示されます。

     ![[プロパティ] ウィンドウと、Greetings ファイル名が含まれる [ソリューション エクスプローラー] ウィンドウ](../media/exploreide-greetingsfilename.png "[プロパティ] ウィンドウと、Greetings ファイル名が含まれる [ソリューション エクスプローラー] ウィンドウのスクリーンショット")     

## <a name="design-the-user-interface-ui"></a>ユーザー インターフェイス (UI) のデザイン

このアプリケーションに、次の 3 種類のコントロールを追加します: <xref:System.Windows.Controls.TextBlock> コントロール、2 つの <xref:System.Windows.Controls.RadioButton> コントロール、<xref:System.Windows.Controls.Button> コントロール。

### <a name="add-a-textblock-control"></a>TextBlock コントロールを追加する

1. **Ctrl**+**Q** と入力し、検索ボックスを有効にして「**ツールボックス**」と入力します。 結果リストから **[表示] > [ツールボックス]** を選択します。

1. **[ツールボックス]** で、 **[コモン WPF コントロール]** ノードを展開し、TextBlock コントロールを表示します。

     ![TextBlock コントロールが強調表されているツールボックス](../media/exploreide-textblocktoolbox.png "TextBlock コントロールが強調表されている [ツールボックス] ウィンドウのスクリーンショット")

1. **TextBlock** 項目を選択してデザイン サーフェイス上のウィンドウにドラッグし、TextBlock コントロールをデザイン サーフェイスに追加します。 ウィンドウの上部付近の中央にコントロールを配置します。

    ウィンドウは次の図のようになります。

    ![Greetings フォームの TextBlock コントロール](../media/exploreide-greetingswithtextblockonly.png "Greetings フォームの TextBlock コントロールのスクリーンショット")

   XAML マークアップは、次の例のようになります。

    ```xaml
    <Grid>
        <TextBlock HorizontalAlignment="Left" Margin="387,60,0,0" TextWrapping="Wrap" Text="TextBlock" VerticalAlignment="Top"/>
    </Grid>
    ```

### <a name="customize-the-text-in-the-text-block"></a>テキスト ブロックのテキストをカスタマイズする

1. XAML ビューで、**TextBlock** のマークアップを探し、**Text** 属性を `TextBox` から `Select a message option and then choose the Display button.` に変更します

   XAML マークアップは、次の例のようになります。

   ```xaml
   <Grid>
       <TextBlock HorizontalAlignment="Left" Margin="387,60,0,0" TextWrapping="Wrap" Text="Select a message option and then choose the Display button." VerticalAlignment="Top"/>
   </Grid>
   ```

1. 必要に応じて、TextBlock をもう一度中央揃えし、**Ctrl + S** キーを押すか、 **[ファイル]** メニュー項目を使って、変更を保存します。

次に、2 つの [RadioButton](/dotnet/framework/wpf/controls/radiobutton) コントロールをフォームに追加します。

### <a name="add-radio-buttons"></a>オプション ボタンを追加する

1. **[ツールボックス]** で、**RadioButton** コントロールを探します。

     ![RadioButton コントロールが選択された [ツールボックス] ウィンドウ](../media/exploreide-radiobuttontoolbox.png "RadioButton コントロールが選択された [ツールボックス] ウィンドウのスクリーンショット")

1. **RadioButton** 項目を選択してデザイン サーフェイス上のウィンドウにドラッグし、RadioButto コントロールを 2 つデザイン サーフェイスに追加します。 TextBlock コントロールの下にボタンが並んで表示されるように、ボタンを移動します (ボタンを選択し、方向キーを使います)。

   ウィンドウは、次のようになります。

   ![TextBlock と 2 つのラジオ ボタンが含まれる Greetings フォーム](../media/exploreide-greetingswithradiobuttons.png "TextBlock と 2 つのラジオ ボタンが含まれる Greetings フォームのスクリーンショット")

1. 左側の RadioButton コントロールの **[プロパティ]** ウィンドウで、 **[Name]** プロパティ ( **[プロパティ]** ウィンドウの一番上のプロパティ) を `HelloButton`に変更します。

    ![RadioButton のプロパティ ウィンドウ](../media/exploreide-buttonproperties.png "RadioButton のプロパティ ウィンドウのスクリーンショット")

1. 右側の RadioButton コントロールの **[プロパティ]** ウィンドウで、 **[Name]** プロパティを `GoodbyeButton` に変更し、変更を保存します。

次に、各 RadioButton コントロールの表示テキストを追加します。 次の手順では、RadioButton コントロールの **[Content]** プロパティを更新します。

### <a name="add-display-text-for-each-radio-button"></a>各オプション ボタンの表示テキストを追加する

1. デザイン サーフェイスで、HelloButton のショートカット メニューを開きます。HelloButton の右マウス ボタンを押し、 **[テキストの編集]** を選択し、「`Hello`」と入力します。

1. GoodbyeButton のショートカット メニューを開きます。GoodbyeButton の右マウス ボタンを押し、 **[テキストの編集]** を選択し、「`Goodbye`」と入力します。

   XAML マークアップは次の例のようになります。

   ```xaml
   <Grid>
        <TextBlock HorizontalAlignment="Left" Margin="252,47,0,0" TextWrapping="Wrap" Text="Select a message option and then choose the Display button." VerticalAlignment="Top"/>
        <RadioButton x:Name="HelloButton" Content="Hello" HorizontalAlignment="Left" Margin="297,161,0,0" VerticalAlignment="Top"/>
        <RadioButton x:Name="GoodbyeButton" Content="Goodbye" HorizontalAlignment="Left" Margin="488,161,0,0" VerticalAlignment="Top"/>
   </Grid>
   ```

### <a name="set-a-radio-button-to-be-checked-by-default"></a>チェックマークが既定で付けられるようにラジオ ボタンを設定する

この手順では、2 つのラジオ ボタンのいずれかが常に選択されるように、HelloButton に既定でチェックマークが付けられるように設定します。

1. XAML ビューで、HelloButton のマークアップを見つけます。

1. **IsChecked** 属性を追加し、**True** に設定します。 具体的には、`IsChecked="True"` を追加します。

   XAML マークアップは次の例のようになります。

   ```xaml
   <Grid>
        <TextBlock HorizontalAlignment="Left" Margin="252,47,0,0" TextWrapping="Wrap" Text="Select a message option and then choose the Display button." VerticalAlignment="Top"/>
        <RadioButton x:Name="HelloButton" Content="Hello" IsChecked="True" HorizontalAlignment="Left" Margin="297,161,0,0" VerticalAlignment="Top"/>
        <RadioButton x:Name="GoodbyeButton" Content="Goodbye" HorizontalAlignment="Left" Margin="488,161,0,0" VerticalAlignment="Top"/>
   </Grid>
   ```

最後に追加する UI 要素は、[Button](/dotnet/framework/wpf/controls/button) コントロールです。

### <a name="add-the-button-control"></a>Button コントロールを追加する

1. **[ツールボックス]** で、 **Button** コントロールを探し、デザイン サーフェイスの RadioButton コントロールの下に追加します。デザイン ビュー内のフォームにドラッグすると追加されます。

1. XAML ビューで、Button コントロールの **[Content]** の値を `Content="Button"` から `Content="Display"`に変更し、変更を保存します。

     ウィンドウは次の図のようになります。

     ![コントロール ラベルが含まれる Greetings フォーム](media/exploreide-greetingswithcontrollabels-cs.png "コントロール ラベルが含まれる Greetings フォーム")

   XAML マークアップは次の例のようになります。

   ```xaml
   <Grid>
        <TextBlock HorizontalAlignment="Left" Margin="252,47,0,0" TextWrapping="Wrap" Text="Select a message option and then choose the Display button." VerticalAlignment="Top"/>
        <RadioButton x:Name="HelloButton" Content="Hello" IsChecked="True" HorizontalAlignment="Left" Margin="297,161,0,0" VerticalAlignment="Top"/>
        <RadioButton x:Name="GoodbyeButton" Content="Goodbye" HorizontalAlignment="Left" Margin="488,161,0,0" VerticalAlignment="Top"/>
        <Button Content="Display" HorizontalAlignment="Left" Margin="377,270,0,0" VerticalAlignment="Top" Width="75"/>
   </Grid>
   ```

### <a name="add-code-to-the-display-button"></a>Display ボタンにコードを追加する

このアプリケーションを実行すると、ユーザーがラジオ ボタンを選択した後で **[Display]** ボタンを選択したときに、メッセージ ボックスが表示されます。 1 つのメッセージ ボックスには "Hello" と表示され、もう 1 つメッセージ ボックスには "Goodbye" と表示されます。 この動作を作成するために、*Greetings.xaml.cs*の `Button_Click` イベントにコードを追加します。

1. デザイン サーフェイスで、 **[Display]** ボタンをダブルクリックします。

     *Greetings.xaml.cs* が開き、`Button_Click` イベントにカーソルが表示されます。

    ```csharp
    private void Button_Click_1(object sender, RoutedEventArgs e)
    {

    }
    ```

1. 次のコードを入力します。

    ```csharp
    if (HelloButton.IsChecked == true)
    {
         MessageBox.Show("Hello.");
    }
    else if (GoodbyeButton.IsChecked == true)
    {
        MessageBox.Show("Goodbye.");
    }
    ```

1. アプリケーションを保存します。

## <a name="debug-and-test-the-application"></a>アプリケーションのデバッグとテスト

次に、アプリケーションをデバッグしてエラーを探し、両方のメッセージ ボックスが正しく表示されることをテストします。 以下の指示にデバッガーをビルドして起動する方法が示されていますが、詳細については、後で「[WPF アプリケーション (WPF) のビルド](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)」および「[WPF のデバッグ](../../debugger/debugging-wpf.md)」を参照することもできます。

### <a name="find-and-fix-errors"></a>エラーの検出と修正

この手順では、前に *MainWindow.xaml* ファイルの名前を変更することで引き起こしたエラーを見つけます。

#### <a name="start-debugging-and-find-the-error"></a>デバッグを開始し、エラーを見つける

1. **F5** キーを押すか、 **[デバッグ]** 、 **[デバッグの開始]** の順に選択して、デバッガーを起動します。

   **[ブレーク モード]** ウィンドウが表示されます。 **[出力]** ウィンドウに、IOException が発生し、リソース 'mainwindow.xaml' が見つけられないことが示されます。

   ![IOException メッセージ](../media/exploreide-ioexception.png "IOException メッセージのスクリーンショット")

1. **[デバッグ]**  >  **[デバッグの停止]** の順に選択し、デバッガーを停止します。

このチュートリアルの最初で *MainWindow.xaml* の名前を *Greetings.xaml* に変更しましたが、このコードではアプリケーションのスタートアップ URI として *MainWindow.xaml* が指定されたままになっているため、プロジェクトを起動できません。

#### <a name="specify-greetingsxaml-as-the-startup-uri"></a>スタートアップ URI として Greetings.xaml を指定する

1. **ソリューション エクスプローラー**で、*App.xaml* ファイルを開きます。

1. `StartupUri="MainWindow.xaml"` を `StartupUri="Greetings.xaml"` に変更し、変更を保存します。

デバッガーを再度起動します (**F5** を押します)。 アプリケーションの **Greetings** ウィンドウが表示されます。 アプリケーション ウィンドウを閉じ、デバッグを停止します。

### <a name="debug-with-breakpoints"></a>ブレークポイントを使用してデバッグする

ブレークポイントをいくつか追加することで、デバッグ中にコードをテストできます。 ブレークポイントを追加するには、 **[デバッグ]**  >  **[ブレークポイントの設定/解除]** の順に選択するか、中断するコード行の横のエディター ウィンドウの左端の余白をクリックするか、**F9** キーを押します。

#### <a name="add-breakpoints"></a>ブレークポイントを追加する

1. *Greetings.xaml.cs* を開き、`MessageBox.Show("Hello.")` という行を選択します。

1. **[デバッグ]** 、 **[ブレークポイントの設定/解除]** の順に選択して、メニューからブレークポイントを追加します。

     コード行の横の、エディター ウィンドウの左端の余白部分に、赤い円が表示されます。

1. `MessageBox.Show("Goodbye.")`という行を選択します。

1. **F9** キーを押してブレークポイントを追加し、**F5** キーを押してデバッグを開始します。

1. **[Greetings]** ウィンドウで、 **[Hello]** オプション ボタンを選択してから、 **[Display]** ボタンを選択します。

    `MessageBox.Show("Hello.")` という行が黄色で強調表示されます。 IDE の下部では、[自動変数]、[ローカル]、[ウォッチ] の各ウィンドウが左側にまとめてドッキングされ、[呼び出し履歴]、[ブレークポイント]、[例外設定]、[コマンド]、[イミディエイト]、[出力] の各ウィンドウが右側にまとめてドッキングされます。

    ![デバッガーでのブレークポイント](media/exploreide-debugbreakpoint.png "デバッガーでのブレークポイントのスクリーンショット")

1. メニュー バーで **[デバッグ]**  >  **[ステップ アウト]** の順に選択します。

     アプリケーションの実行が再開され、メッセージ ボックスに "Hello" と表示されます。

1. メッセージ ボックスの **[OK]** を選択して閉じます。

1. **[Greetings]** ウィンドウで、 **[Goodbye]** オプション ボタンを選択し、 **[Display]** ボタンを選択します。

     `MessageBox.Show("Goodbye.")` という行が黄色で強調表示されます。

1. **F5** キーを押してデバッグを続行します。 メッセージ ボックスが表示されたら、メッセージ ボックスの **[OK]** を選択して、閉じます。

1. アプリケーション ウィンドウを閉じ、デバッグを停止します。

1. メニュー バーで、 **[デバッグ]**  >  **[すべてのブレークポイントを無効にする]** の順に選択します。

### <a name="build-a-release-version-of-the-application"></a>アプリケーションのリリース バージョンのビルド

すべてが機能することを確認したら、アプリケーションのリリース ビルドを準備できます。

1. メイン メニューで、 **[ビルド]**  >  **[ソリューションのクリーン]** の順に選択して、前のビルドで作成された中間ファイルと出力ファイルを削除します。 この作業は必須ではありませんが、デバッグ ビルドの出力がクリーンアップされます。

1. ツールバー上のドロップダウン コントロール (現時点で [デバッグ] になっている) を使って、HelloWPFApp のビルド構成を **[デバッグ]** から **[リリース]** に変更します。

1. **[ビルド]**  >  **[ソリューションのビルド]** を選択して、ソリューションをビルドします。

これでこのチュートリアルは完了です。 ビルドした *.exe* は、ソリューションとプロジェクトのディレクトリ ( *...\HelloWPFApp\HelloWPFApp\bin\Release*) の下にあります。

## <a name="next-steps"></a>次の手順

これでこのチュートリアルは完了です。 さらに詳しく学習するには、引き続き以下のチュートリアルをご覧ください。

> [!div class="nextstepaction"]
> [さらに WPF のチュートリアルを続ける](/dotnet/framework/wpf/getting-started/wpf-walkthroughs/)

## <a name="see-also"></a>関連項目

- [生産性に関するヒント](../../ide/productivity-features.md)
