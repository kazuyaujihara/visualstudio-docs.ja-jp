---
title: グラフィックス診断の概要 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 59131181-1caa-4b7f-be4b-e84709634edf
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 84c55f9568cc227d067875d7579a99acb81f12a2
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975258"
---
# <a name="getting-started-with-visual-studio-graphics-diagnostics"></a>Visual Studio グラフィックス診断の使用を開始する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このセクションでは、まずグラフィックス診断を初めて使用するための準備をしてから、Direct3D アプリケーションのフレームをキャプチャして Graphics Analyzer でそれらを確認します。

## <a name="requirements"></a>必要条件
 Visual Studio 2015 でグラフィックス診断を使用するには、次のいずれかのエディションが必要です。

- Visual Studio 2015 Enterprise

- Visual Studio 2015 Professional

- Visual Studio 2015 Community

  [!INCLUDE[downloadvs](../includes/downloadvs-md.md)]

### <a name="windows-10-prerequisites"></a>Windows の 10 の前提条件
 Windows のオプション機能の "*グラフィック ツール*" は Windows 10 でのグラフィックス診断に必要なキャプチャと再生のインフラストラクチャを提供します。

 グラフィック ツールをインストールする方法の詳細については、「[Windows 10 のグラフィック ツールをインストールする](#InstallGraphicsTools)」を参照してください。

### <a name="windows-81-prerequisites"></a>Windows 8.1 の前提条件
 Windows 8.1 の Windows Software Development Kit (SDK) は、Windows 8.1 のグラフィックス診断に必要なキャプチャと再生のインフラストラクチャを提供し、Windows 8.1 と Windows 8 用の開発をサポートします。

 [Windows 8.1 用 Windows ソフトウェア開発キット (SDK) のダウンロードします。](https://msdn.microsoft.com/windows/desktop/bg162891.aspx)

 Windows 8.1 を実行する開発用コンピューターから、Windows 10 を実行しているリモート再生コンピューターを使用するには、開発用コンピューターに Windows 10 SDK をインストールして、再生コンピューターにオプションのグラフィック ツール機能をインストールする必要があります。

##  <a name="InstallGraphicsTools"></a> Windows 10 用のグラフィック ツールをインストールする
 Windows 10 では、グラフィックス診断のインフラストラクチャが、"*グラフィック ツール*" と呼ばれる Windows のオプション機能によって提供されます。 この機能は、キャプチャするアプリが以前のバージョンの Windows を対象にしているかどうか、またはどのバージョンの Direct3D を使用しているかに関係なく、Windows 10 でグラフィックス情報をキャプチャおよび再生するために必要です。 グラフィック ツール機能を事前にインストールすることができます。それ以外の場合は、Visual Studio からグラフィックス診断セッションを最初に開始するときに、オンデマンドでインストールされます。

#### <a name="to-install-graphics-tools-for-windows-10"></a>Windows 10 用のグラフィック ツールをインストールするには

1. **開始**] メニューの [選択**設定**します。 **設定**ダイアログが表示されます。

2. **設定**ダイアログ ボックスで、選択**システム**を選択し、**アプリがインストールされている**システム設定の一覧から。

3. 右側にある、**設定**ダイアログ ボックスで、選択**省略可能な機能を管理する****アプリおよび機能がインストールされている**します。 **[オプション機能の管理]** ダイアログが表示されます。

4. **[オプション機能の管理]** ダイアログで、**[機能の追加]** を選択します。 インストールできるオプション機能の一覧が表示されます。

5. 機能の一覧から **[グラフィック ツール]** を選択して、**[インストール]** を選択します。

   グラフィック ツールの機能は Windows 10 SDK をインストールするときにも、自動的にインストールされます。

> [!TIP]
>  Windows 10 のオプションのグラフィック ツール機能は、コマンド ライン キャプチャ プログラム **dxcap.exe** など、軽量のキャプチャおよび再生機能を提供しており、開発者用ツールがインストールされていないコンピューターでサポート、テスト、および診断を行うシナリオで利用できます。 詳細については、「[コマンド ライン キャプチャ ツール](../debugger/command-line-capture-tool.md)」のトピックを参照してください。

## <a name="using-graphics-diagnostics-for-the-first-time"></a>グラフィックス診断を初めて使用する
 これで、必要なものがすべて揃い、グラフィックス診断の使用を開始する準備が整いました。 以下の手順に実行します。

### <a name="1---create-a-direct3d-app"></a>1 -、Direct3D アプリを作成する
 独自の Direct3D アプリが既にある場合は、グラフィックス診断を試すことができます。 そうでない場合は、コード ギャラリーの使用可能な Direct3D サンプルの 1 つを使用できます。

- Visual Studio 2015 を使用して Windows 10 では、direct3d12 のグラフィックス診断を試すを再試行してください、 [direct3d12 UAP サンプル](https://code.msdn.microsoft.com/Direct3D-12-UAP-Sample-ecb1779f)Windows 10 用です。

- グラフィックス診断と direct3d11 を Windows 10 または Windows 8.1 には、使用することができます、 **DirectX アプリ (ユニバーサル Windows)** または**DirectX アプリ (Windows 8.1)** プロジェクト テンプレート。 または、さらに興味深いものに試してみて、 [DirectX marble maze ゲームのサンプル](https://code.msdn.microsoft.com/windowsapps/DirectX-Marble-Maze-Game-e4806345)Windows 8.1 用。

  先に進む前に、アプリをビルドできるかどうかを確認します。

### <a name="2---start-a-graphics-diagnostics-session"></a>2-グラフィックス診断セッションを開始する
 これで、最初のグラフィックス診断のセッションを開始する準備ができました。 Visual Studio のメイン メニューで、選択**デバッグ、グラフィックス診断の開始**、キーを押すか**alt キーを押しながら f5 キー**します。 これで、グラフィックス診断の下でアプリが開始され、Visual Studio の診断セッションのウィンドウが表示されます。

> [!IMPORTANT]
>  Windows 10 でアプリを実行しており、オプションのグラフィック ツール機能をまだインストールしていない場合は、今すぐインストールするよう求められます。 インストールは、Windows 10 でグラフィックス診断を使用する前に済ませておく必要があります。

### <a name="3---capture-frames"></a>3 - フレームをキャプチャする
 アプリが起動すると、すぐにフレームをキャプチャできます。

##### <a name="to-capture-single-frames"></a>1 つのフレームをキャプチャするには

-   Visual Studio の [グラフィックス] ツール バーまたは診断セッション ウィンドウで、**[フレームのキャプチャ]** を選択します。 または、アプリにフォーカスがある場合は、キーを押す**Print Screen**します。

##### <a name="to-capture-a-sequence-of-frames"></a>フレームのシーケンスをキャプチャするには

- Visual Studio の診断セッション ウィンドウの **[キャプチャするフレーム]** にシーケンスでキャプチャするフレームの数を設定し、1 つのフレームをキャプチャするための前述の方法のいずれかに従ってシーケンスをキャプチャします。

   1 つのフレームをもう一度キャプチャするには、次のように設定します。**キャプチャするフレーム**に`1`します。

  キャプチャが終了したら、アプリケーションを終了するか、[グラフィックス] ツールバーまたは診断セッション ウィンドウから **[停止]** ボタンをクリックします。

### <a name="4--examine-captured-frames-in-the-graphics-analyzer"></a>4 – Graphics Analyzer でキャプチャされたフレームを確認する
 これで、キャプチャしたフレームを詳しく調べる準備ができました。 フレーム分析を開始するには、診断セッション ウィンドウから確認するフレームのフレーム番号を選択します。 これで、フレームが **Graphics Analyzer** で表示され、ここでグラフィックス診断ツールを使用して、アプリがどのように Direct3D を使用しているかを調べてレンダリングの問題を追跡したり、**フレーム分析**ツールを使用して、パフォーマンスを理解したりできます。

 診断セッション ウィンドウで間違ったフレームを選択した場合や、別のフレームを確認する場合は、Graphics Analyzer から新しいフレームを選択できます。 グラフィックス ログ ウィンドウの **[レンダー ターゲット]** タブで、レンダー ターゲットのイメージの下にある **[フレーム一覧]** を展開し、確認する別のフレームを選択します。

 Graphics Analyzer ツールを一緒に使用する方法の詳細については、次を参照してください。、[例](../debugger/graphics-diagnostics-examples.md)します。

## <a name="see-also"></a>関連項目
 [Direct3D 12 グラフィックス](http://msdn.microsoft.com/52094ae3-3b44-4689-9ee7-1ba1b3a779cb)
