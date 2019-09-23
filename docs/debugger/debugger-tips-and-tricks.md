---
title: デバッガーのヒントとコツ
description: Visual Studio デバッガーでサポートされている、あまり知られていない機能のいくつかについて説明します。
ms.custom: seodec18
ms.date: 06/15/2018
ms.topic: conceptual
helpviewer_keywords:
- stepping
- debugging [Visual Studio], execution control
- execution, controlling in debugger
ms.assetid: 5262d8b1-2648-429e-85d5-90fcaadfb362
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 61c1efea7340425090adbdd1c9bc865c4a056d42
ms.sourcegitcommit: 0e482cfc15f809b564c3de61646f29ecd7bfcba6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70987762"
---
# <a name="learn-productivity-tips-and-tricks-for-the-debugger-in-visual-studio"></a>Visual Studio でのデバッガーの生産性に関するヒントとテクニックについて説明します。

このトピックでは、Visual Studio デバッガーの生産性に関するヒントとテクニックについて説明します。 デバッガーの基本的な機能については、「[デバッガーの概要](../debugger/debugger-feature-tour.md)」を参照してください。 このトピックでは、機能ツアーに含まれていないいくつかの領域について説明します。

## <a name="pin-data-tips"></a>データのピン留めに関するヒント

デバッグ中にデータのヒントを頻繁にポイントする場合は、変数のデータヒントを固定して、すぐにアクセスできるようにすることができます。 変数は、再起動後も固定されたままです。 データヒントをピン留めするには、ピンアイコンをクリックします。 複数の変数をピン留めすることができます。

![データヒントのピン留め](../debugger/media/dbg-tips-data-tips-pinned.png "PinningDataTip")

## <a name="edit-your-code-and-continue-debugging-c-vb-c"></a>コードを編集してデバッグをC#続行する ( C++、VB、)

Visual Studio でサポートされているほとんどの言語では、デバッグセッション中にコードを編集してデバッグを続行できます。 この機能を使用するには、デバッガーで一時停止中にカーソルを使用してコードをクリックし、編集を行い、 **F5**キー、 **F10**キー、または**F11**キーを押してデバッグを続行します。

![エディットコンティニュのデバッグ](../debugger/media/dbg-tips-edit-and-continue.gif "Editandcontinue")

機能の使用と機能の制限事項の詳細については、「[エディットコンティニュ](../debugger/edit-and-continue.md)」を参照してください。

## <a name="edit-xaml-code-and-continue-debugging"></a>XAML コードを編集してデバッグを続行する

デバッグセッション中に XAML コードを変更するには、「 [Xaml ホットリロードを使用した実行中の xaml コードの書き込みとデバッグ](xaml-hot-reload.md)」を参照してください。

## <a name="debug-issues-that-are-hard-to-reproduce"></a>再現するのが困難な問題をデバッグする

アプリで特定の状態を再作成するのが困難または時間がかかる場合は、条件付きブレークポイントの使用が役立つかどうかを検討してください。 [条件付きブレーク](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)ポイントとフィルターブレークポイントを使用すると、アプリが目的の状態 (不適切なデータを格納している状態など) になるまで、アプリコードが中断されないようにすることができます。 式、フィルター、ヒットカウントなどを使用して条件を設定できます。

#### <a name="to-create-a-conditional-breakpoint"></a>条件付きブレークポイントを作成するには

1. ブレークポイントアイコン (赤いボール) を右クリックし、 **[条件]** を選択します。

2. **[ブレークポイントの設定]** ウィンドウで、式を入力します。

    ![条件付きブレークポイント](../debugger/media/dbg-multithreaded-conditional-breakpoint.png "Conditionalbreakpoint ポイント")

3. 別の種類の条件に関心がある場合は、 **[ブレークポイントの設定]** ダイアログボックスで [**条件式**の代わりに**フィルター** ] を選択し、フィルターのヒントに従います。

## <a name="configure-the-data-to-show-in-the-debugger"></a>デバッガーに表示するデータの構成

、 C#Visual Basic、およびC++ (C++/cli コードのみ) の場合、debugger [display](../debugger/using-the-debuggerdisplay-attribute.md)属性を使用してどの情報を表示するかをデバッガーに指示できます。 コードC++については、 [Natvis の視覚化](create-custom-views-of-native-objects.md)を使用して同じ操作を行うことができます。

## <a name="change-the-execution-flow"></a>実行フローを変更する

デバッガーがコード行で一時停止したら、マウスを使用して、左側の黄色の矢印ポインターをつかみます。 黄色い矢印ポインターをコード実行パスの別の点に移動します。 次に、F5 キーまたはステップコマンドを使用して、アプリの実行を続行します。

![実行ポインターを移動する](../debugger/media/dbg-tour-move-the-execution-pointer.gif "実行ポインターを移動する")

実行フローを変更することにより、さまざまなコード実行パスをテストしたり、デバッガーを再起動することなくコードを再実行したりできます。

> [!WARNING]
> 多くの場合、この機能には注意する必要があり、ツールヒントに警告が表示されます。 他の警告が表示される場合もあります。 ポインターを移動してアプリを以前のアプリケーション状態に戻すことはできません。

## <a name="track-an-out-of-scope-object-c-visual-basic"></a>スコープ外のオブジェクト (C#、Visual Basic) を追跡する

**[ウォッチ]** ウィンドウのようなデバッガーウィンドウを使用すると、変数を簡単に表示できます。 ただし、**ウォッチ**ウィンドウで変数がスコープ外に出ると、淡色表示になっていることがわかります。アプリのシナリオによっては、変数がスコープ外になった場合でも変数の値が変更されることがあります。また、変数の値を注意深く監視することもできます (たとえば、変数がガベージコレクトされる可能性があります)。 変数のオブジェクト ID を **[ウォッチ]** ウィンドウに作成することで、変数を追跡できます。

#### <a name="to-create-an-object-id"></a>オブジェクト ID を作成するには

1. 追跡する変数の近くにブレークポイントを設定します。

2. デバッガーを起動し (**F5**)、ブレークポイントで停止します。

3. **[ローカル]** ウィンドウで変数を探し ([**デバッグ] > [Windows > ローカル**])、変数を右クリックして **[オブジェクト ID の作成]** を選択します。

    ![オブジェクト ID を作成]する(../debugger/media/dbg-tips-watch-create-object-id.png "Createobjectid")

4. **$** ウィンドウに、 **[ローカル]** ウィンドウを閉じます。 この変数はオブジェクト ID です。

5. オブジェクト ID 変数を右クリックし、 **[ウォッチ式の追加]** を選択します。

詳細については、「[オブジェクト ID を作成する](../debugger/watch-and-quickwatch-windows.md#bkmk_objectIds)」を参照してください。

## <a name="view-return-values-for-functions"></a>関数の戻り値の表示

関数の戻り値を表示するには、コードのステップ実行中に **[自動変数]** ウィンドウに表示される関数を確認します。 関数の戻り値を表示するには、関心のある関数が既に実行されていることを確認します (関数呼び出しで現在停止している場合は、 **F10**キーを1回押します)。 ウィンドウが閉じている場合は、 **[デバッグ > Windows > 自動変数]** を使用して **[自動]** 変数 ウィンドウを開きます。

![自動変数ウィンドウ](../debugger/media/dbg-tips-autos-window.png "Autoswindow")

また、 **[イミディエイト]** ウィンドウに関数を入力して、戻り値を表示することもできます。 ( **Windows > イミディエイトでデバッグ >** 使用して開きます)。

![イミディエイトウィンドウ](../debugger/media/dbg-tips-immediate-window.png "イミディエイトウィンドウ")

また、のように、 **[ウォッチ]** ウィンドウと **[イミディエイト]** ウィンドウ`$ReturnValue`で[擬似変数](../debugger/pseudovariables.md)を使用することもできます。

## <a name="string_visualizer"></a>ビジュアライザー内の文字列の検査

文字列を使用する場合は、書式設定された文字列全体を表示すると便利です。 プレーンテキスト、XML、HTML、または JSON 文字列を表示するには、文字列値を含む変数にマウスポインターを置いた状態で、虫眼鏡アイコン![Visualizericon](../debugger/media/dbg-tips-visualizer-icon.png "ビジュアライザーアイコン")をクリックします。

![文字列ビジュアライザーを開く](../debugger/media/dbg-tips-string-visualizers.png "Openstringvisualizer")

文字列ビジュアライザーは、文字列の種類に応じて文字列の形式が正しくないかどうかを調べるのに役立ちます。 たとえば、空白の**値**フィールドは、ビジュアライザー型によって文字列が認識されないことを示します。 詳細については、「[[文字列ビジュアライザー] ダイアログボックス](../debugger/string-visualizer-dialog-box.md)」を参照してください。

![JSON 文字列ビジュアライザー](../debugger/media/dbg-tips-string-visualizer-json.png "Jsonstringvisualizer")

デバッガーウィンドウに表示されるデータセットや DataTable オブジェクトなど、他のいくつかの型については、組み込みビジュアライザーを開くこともできます。

## <a name="break-into-code-on-handled-exceptions"></a>処理された例外のコードの中断

デバッガーは、ハンドルされない例外でコードにブレークします。 ただし、処理された例外 ( `try/catch`ブロック内で発生する例外など) もバグの原因になる可能性があり、発生した場合は調査する必要があります。 **[例外設定]** ダイアログボックスでオプションを構成することによって、処理された例外のコードに中断するようにデバッガーを構成することもできます。 **[デバッグ > Windows > 例外設定]** を選択して、このダイアログボックスを開きます。

**[例外設定]** ダイアログボックスを使用すると、特定の例外でコードを中断するようにデバッガーに指示できます。 次の図では、が発生する`System.NullReferenceException`たびにデバッガーがコードに分割されます。 詳細については、「[例外の管理](../debugger/managing-exceptions-with-the-debugger.md)」を参照してください。

![[例外設定] ダイアログボックス](../debugger/media/dbg-tips-exception-settings.png "Exceptionsettingsdialogbox")

## <a name="debug-deadlocks-and-race-conditions"></a>デッドロックと競合状態のデバッグ

マルチスレッドアプリに共通する問題の種類をデバッグする必要がある場合、多くの場合、デバッグ中のスレッドの場所を確認するのに役立ちます。 これは、 **[ソースのスレッドを表示]** ボタンを使用して簡単に行うことができます。

#### <a name="to-show-threads-in-your-source-code"></a>ソースコードでスレッドを表示するには

1. デバッグ中に、 **[ソースのスレッドを表示]** する ボタンをクリックし、 **[デバッグ]** ツールバーの [ソース(../debugger/media/dbg-multithreaded-show-threads.png "Threadmarker") ![にスレッドを表示する]] をクリックします。

2. ウィンドウ左端の余白に注目します。 この行には、2つの布スレッドに似*たスレッドマーカーアイコン*![スレッド]マーカー(../debugger/media/dbg-thread-marker.png "threadmarker")が表示されます。 スレッド マーカーは、スレッドが停止している位置を示します。

    スレッドマーカーは、ブレークポイントによって部分的に非表示になっている可能性があります。

3. スレッド マーカーの上にポインターを置きます。 DataTip が表示されます。 データヒントは、停止したスレッドごとに名前とスレッド ID 番号を表示します。

    [[並列スタック] ウィンドウ](../debugger/get-started-debugging-multithreaded-apps.md)でスレッドの場所を表示することもできます。

## <a name="examine-payloads-for-web-services-and-network-resources-uwp"></a>Web サービスとネットワークリソース (UWP) のペイロードを調べる

UWP アプリでは、 `Windows.Web.Http` API を使用して実行されたネットワーク操作を分析できます。 このツールを使用すると、web サービスとネットワークリソースをデバッグできます。 ツールを使用するには、 **[デバッグ > パフォーマンスプロファイラー]** を選択します。 **[ネットワーク]** を選択し、 **[開始]** を選択します。 アプリで、`Windows.Web.Http` を使用するシナリオを実行し、 **[コレクションの停止]** を選択してレポートを生成します。

![ネットワーク使用率プロファイリングツール](../profiling/media/prof-tour-network-usage.png "NetworkUsageProfTool")

概要ビューで操作を選択すると、詳細が表示されます。

![ネットワーク使用率ツールの詳細情報](../profiling/media/prof-tour-network-usage-details.png "DetailedViewNetworkUsage")

詳細については、「[ネットワーク使用率](../profiling/network-usage.md)」を参照してください。

## <a name="modules_window"></a>デバッガーをアプリにアタッチする方法 (C#、 C++、Visual Basic、 F#) について理解を深める

実行中のアプリにアタッチするために、デバッガーは、デバッグしようとしているアプリとまったく同じビルド用に生成されたシンボル (.pdb) ファイルを読み込みます。 場合によっては、シンボルファイルに関するわずかな知識が役に立つことがあります。 **[モジュール]** ウィンドウを使用して、Visual Studio がシンボルファイルを読み込む方法を調べることができます。

デバッグ **[> Windows > モジュール]** を選択して、デバッグ中に **[モジュール]** ウィンドウを開きます。 **[モジュール]** ウィンドウでは、デバッガーがユーザーコードまたは[*マイコード*](../debugger/just-my-code.md)として処理しているモジュール、およびモジュールのシンボルの読み込み状態を知ることができます。 ほとんどのシナリオでは、デバッガーはユーザーコードのシンボルファイルを自動的に検出しますが、.NET framework コード、システムコード、またはサードパーティのライブラリコードをステップイン (デバッグ) する場合は、適切なシンボルファイルを取得するために追加の手順が必要になります。

![[モジュール] ウィンドウでシンボル情報を表示する](../debugger/media/dbg-tips-modules-window.png "Viewシンボル情報")

シンボル情報は、右クリックして **[シンボルの読み込み]** を選択すると、 **[モジュール]** ウィンドウから直接読み込むことができます。

場合によっては、アプリ開発者は、一致するシンボルファイルがないアプリ (フットプリントを削減するため) を配布しますが、後でリリースされたバージョンをデバッグできるように、ビルドの一致するシンボルファイルのコピーを保持します。

デバッガーがコードをユーザーコードとして分類する方法を確認するには、「[マイコードのみ](../debugger/just-my-code.md)」を参照してください。 シンボルファイルの詳細については、「 [Visual Studio デバッガーでのシンボル (.pdb) ファイルとソースファイルの指定](specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)」を参照してください。

## <a name="learn-more"></a>詳細情報

その他のヒントとテクニック、さらに詳しい情報については、次のブログ投稿を参照してください。

- [7 Visual Studio でのデバッグに関する既知のハック](https://devblogs.microsoft.com/visualstudio/7-lesser-known-hacks-for-debugging-in-visual-studio/)
- [7 Visual Studio での非表示の gem](https://devblogs.microsoft.com/visualstudio/7-hidden-gems-in-visual-studio-2017/)

## <a name="see-also"></a>関連項目

[キーボード ショートカット](../ide/productivity-shortcuts.md)
