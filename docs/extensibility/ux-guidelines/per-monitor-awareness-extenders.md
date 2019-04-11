---
title: Visual Studio の extender のモニターごとの認識をサポート
titleSuffix: ''
description: あたり-モニター-認識の Visual Studio 2019 で使用できる新しいエクステンダーのサポートについて説明します。
ms.date: 04/09/2019
helpviewer_keywords:
- Visual Studio, PMA, per-monitor-awareness, extenders, Windows Forms
- Per-Monitor Awareness support for extenders
ms.assetid: ''
author: rub8n
ms.author: rurios
manager: anthc
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.topic: reference
ms.workload:
- multiple
ms.openlocfilehash: 42de73a29e053066c0fbeca72ca3511b58b2fa7e
ms.sourcegitcommit: 0a2fdc23faee77187e10a1c19665ba5a1ac68e72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/10/2019
ms.locfileid: "59477694"
---
# <a name="per-monitor-awareness-support-for-visual-studio-extenders"></a>Visual Studio の extender のモニターごとの認識をサポート

Visual Studio 2019 より前のバージョンには、モニターごとの DPI に注意してください (PMA) ではなく、システムに設定、DPI 認識コンテキストが必要があります。 認識結果、システムを実行して (例: ぼやけてフォントまたはアイコン) 低下視覚エクスペリエンスでたびに Visual Studio は、複数のモニターの別のスケール ファクターでレンダリングする必要がある。 またはへのリモート接続が別の表示構成 (例: 別のコンピューターWindows スケーリング)。

Visual Studio 2019 の DPI 認識のコンテキストでは、定義されている一般的なシステム構成ではなく、セットとしてモニターがホストされている表示の構成に合わせて表示するために、対応を可能にする Visual Studio です。 最終的に鮮明な UI PMA サポートを実装する領域に変換します。

参照してください、 [Windows 上の高 DPI Desktop Application Development](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)ドキュメント、用語と全体的なシナリオの詳細については、このドキュメントで説明します。

## <a name="quickstart"></a>クイック スタート
- Visual Studio が PMA モードで実行されていることを確認 (を参照してください**を有効にする PMA**)

- 一連の一般的なシナリオの間で、拡張機能のしくみを正しく検証 (を参照してください**PMA 問題について、拡張機能をテスト**)

- 問題が見つかった場合必要があります、新しい PMA nugget パッケージを追加する診断、戦略とこのドキュメントで説明した推奨事項を使用して問題を修正

## <a name="enabling-pma"></a>PMA を有効にします。
Visual Studio で PMA を有効にするには、次の要件を満たす必要があります。
1)  Windows 10 April 2018 Update (v1803 RS4) またはそれ以降
2)  .NET framework 4.8 RTM 以上 (現在スタンドアロン プレビューまたは最近のバンドルとして出荷されます Windows Insider ビルド)
3)  Visual Studio 2019、 [「異なるピクセル密度の画面のレンダリングの最適化」](https://docs.microsoft.com/visualstudio/ide/reference/general-environment-options-dialog-box?view=vs-2019)オプションを有効に

これらの要件が満たされると、Visual Studio は、プロセス全体で PMA を有効に自動的にします。

## <a name="testing-your-extensions-for-pma-issues"></a>PMA 問題について、拡張機能のテスト

Visual Studio には、WPF、Windows フォーム、Win32、HTML/JS UI フレームワークが正式にサポートしています。 Visual Studio が PMA モードに切り替わる、さまざまな UI スタック動作が異なる。 そのため、UI フレームワークに関係なくは、すべての UI が PMA に準拠していることを確認するテスト パスが実行されることをお勧めします。

UI フレームワークに関係なく、拡張機能をサポートする次の一般的なシナリオを検証することをお勧めします。

1. 単一の監視環境のスケール ファクターを変更して、アプリケーションが実行されている *
    - このシナリオにより、UI が動的な Windows DPI の変更に応答しているテスト

2. アプリケーションの実行中に、プライマリ レプリカと接続しているモニターに付属のモニターが設定されているラップトップにプライマリよりも別のスケール ファクターがドッキング ドッキング解除します。
    - このシナリオは、DPI の変更、表示を動的に処理の追加や削除、表示する UI が応答をテストします。

3. 複数のモニターの別のスケール ファクターであり、それらの間、アプリケーションの移行します。
    - このシナリオにより、UI がディスプレイ DPI の変更に応答しているテスト
    
4. ローカルとリモート コンピューターは、プライマリ モニターの別のスケール ファクターがある場合に、マシンにリモート アクセスします。
    - このシナリオにより、UI が動的な Windows DPI の変更に応答しているテスト

UI が問題があるかどうかの予備テストは、コードがいずれかを利用するかどうか、 *Microsoft.VisualStudio.Utilities.Dpi.DpiHelper*または*Microsoft.VisualStudio.PlatformUI.DpiHelper*クラス。 これらの古い DpiHelper クラスのみのシステム DPI の認識をサポートしており、プロセスが PMA と正しく機能しない常にします。

これらの DpiHelpers の一般的な使用方法は、ようになります。

```cs
Point screenTopRight = logicalBounds.TopRight.LogicalToDeviceUnits();

POINT screenIntTopRight = new POINT
{
    x = (int)screenTopRIght.X,
    y = (int)screenTopRIght.Y
}

IntPtr monitor = NativeMethods.MonitorFromPoint(screenIntTopRight, NativeMethods.Monitor_DEFAULTTONEARST);
```

ウィンドウの論理境界を表す四角形は、前の例では、MonitorFromPoint 正確なモニターへのポインターを返すためにデバイス座標が必要とするネイティブのメソッドに渡すことができるようにデバイス単位に変換されます。

### <a name="classes-of-issues"></a>問題のクラス

PMA for Visual Studio が有効の場合、UI は、いくつかの一般的な方法で問題をレプリケートするでした。 最も、全部ではありませんこれらの問題の発生することがサポートされている UI フレームワークの Visual Studio のいずれか。 さらに、これらの問題がもときの UI でホストされている混合モードの DPI スケーリング シナリオを実行することができます (、Windows を参照してください[ドキュメント](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)の詳細は)。 

#### <a name="win32-window-creation"></a>Win32 ウィンドウの作成
CreateWindow() または CreateWindowEx() で windows を作成するときに一般的なパターンは座標 0, 0 にあるウィンドウ (プライマリ ディスプレイ上/左隅) を作成しに移動しその最後の位置。 ただし、DPI をトリガーするウィンドウが生じることが変更されたは、メッセージまたはイベントでは、他の UI メッセージまたはイベントを再トリガーし、望ましくない動作やレンダリングにつながることができます。

#### <a name="wpf-element-placement"></a>WPF 要素の配置
古い Microsoft.VisualStudio.Utilities.Dpi.DpiHelper を使用して WPF 要素を移動するときに左座標可能性がありますが正しく計算されない要素は、プライマリ以外の場合は DPI。

#### <a name="serialization-of-ui-element-sizes-or-positions"></a>UI 要素のサイズまたは位置のシリアル化
UI のサイズや位置に保存されていたものとは異なる DPI コンテキストに復元されるたびには配置され、適切なサイズします。 これは、正確なモニターへのポインターを返すためにデバイス座標が必要とする MonitorFromPoint Win32 メソッドに渡すことができるように、ウィンドウの境界の論理がデバイス単位に変換されるために発生します。

#### <a name="incorrect-scaling"></a>不適切なスケーリング
プライマリの DPI に作成される UI 要素をさまざまな dpi ディスプレイに移動すると変更がないため、そのコンテンツが大きすぎるか小さすぎるため、正しく拡大縮小されます。

#### <a name="incorrect-bounding"></a>正しくない境界
同様に、スケーリングの問題を UI 要素が計算されます、プライマリの DPI のコンテキストで正しく、境界が、新しい境界を正しく計算がプライマリ以外の DPI に移動するときにありません。 そのため、コンテンツ ウィンドウ最終的が小さすぎるか大きすぎるホスティングの UI は、空の領域でクリッピングの結果と比較されます。

#### <a name="drag--drop"></a>ドラッグ アンド ドロップ
たびに混合モード DPI シナリオ (例: さまざまな UI 要素でプライマリと非プライマリの両方の DPI コンテキストの表示)、ドラッグ アンド ドロップの内部座標でしたが誤って計算された、その結果、最終的なドロップ位置の最後が正しくありません。

#### <a name="out-of-process-ui"></a>プロセス外の UI
一部の UI にはアウト プロセスが作成され、これが以前のレンダリングの問題のいずれかを導入、作成した外部プロセスは、Visual Studio よりも、さまざまな解像度認識モードでは場合、。

#### <a name="windows-forms-controls-images-or-windows-not-displaying"></a>Windows フォーム コントロール、イメージ、または windows に表示されません。
この問題の主な原因の 1 つは、開発者がコントロールまたは異なる DpiAwarenessContext ウィンドウに 1 つ DpiAwarenessContext でウィンドウの親を変更しようとしています。 

次の図は、動作をホストしているスレッドが明示的に変更されない限り、windows での親で現在の Windows オペレーティング システムの制限を示してください。

![適切な親動作のスクリーン ショット](../../extensibility/ux-guidelines/media/PMA-parenting-behavior.PNG)

その結果、サポートされていないモード間の親子リレーションシップを設定した場合は、失敗し、コントロールまたはウィンドウが表示されない期待どおりにします。

### <a name="diagnosing-issues"></a>問題を診断します。
PMA 関連の問題を特定する際に考慮すべき多くの要素があります。 

1. UI または API 想定論理またはデバイスの値。
    - WPF の UI と Api の論理値を使用して通常 (が常にではありません)
    - デバイスの値が通常使用 Win32 UI と Api

2. 値は、場所はでしょうか。
    - その他の UI または API からの値を受信している場合は、渡すデバイスまたは論理値は。
    - 場合は、複数のソースから値を受け取るすべて使用/を期待するのと同じ値の型変換は実行を一致させる必要がありますか。

3. 使用中の UI の定数とどのようなフォームを使用しているでしょうか。

4. スレッドは、値の適切な DPI のコンテキストで受信しますか?
    - CLMM を有効にする変更が、コード パスを適切なコンテキストに配置する必要があります一般に、ただし、メイン メッセージ ループまたはイベント フローの外部で実行する作業は、誤った DPI のコンテキストで実行可能性があります。

5. 値は、DPI のコンテキスト境界を越えるでしょうか。
    - ドラッグ アンド ドロップは、座標が DPI コンテキストを通過できる一般的な状況です。 ウィンドウは、正常に実行しようとしましたが、場合によっては、ホストの UI が一致するコンテキストの境界を確実に変換作業を行う必要があります。

### <a name="pma-nugget-package"></a>PMA Nugget パッケージ
Microsoft.VisualStudio.DpiAwareness NuGet パッケージでは、新しい DpiAwarness ライブラリを確認できます。

### <a name="recommended-tools"></a>推奨されるツール
次のツールは、Visual Studio でサポートされているさまざまな UI スタックの一部の間で PMA 関連の問題をデバッグできます。

#### <a name="snoop"></a>Snoop
Snoop とは、いくつか追加の機能がない、組み込みの Visual Studio の XAML ツールを含む XAML のデバッグ ツールです。 さらに、Snoop を表示し、WPF の UI を調整できる Visual Studio を積極的にデバッグする必要はありません。 Snoop を PMA 問題の診断に役立つことができる 2 つの主な方法は、配置の論理座標やサイズの境界を検証するためと、UI が適切な DPI を検証するためです。
 
#### <a name="visual-studio-xaml-tools"></a>Visual Studio の XAML ツール
Snoop などのように Visual Studio で XAML ツールは PMA の問題を診断役立ちます。 可能性の高い原因が見つかったらは、ブレークポイントを設定し、UI の境界と現在の DPI を検査する、デバッグ ウィンドウと同様に、[Live Visual Tree] ウィンドウを使用します。

## <a name="strategies-for-fixing-pma-issues"></a>PMA 問題を修正するための戦略

### <a name="replacing-dpihelper-calls"></a>DpiHelper 呼び出しを置き換える
ほとんどの場合、PMA で UI の問題の修正を要約するマネージ コードで、以前の呼び出しを置き換えます。*Microsoft.VisualStudio.Utilities.Dpi.DpiHelper*と*Microsoft.VisualStudio.PlatformUI.DpiHelper*クラスの新しいへの呼び出しで、 *Microsoft.VisualStudio.Utilities.DpiAwareness*ヘルパー クラス。 

古い置換の呼び出しを伴う、ネイティブ コードに対して*VsUI::CDpiHelper*新しいへの呼び出しにクラス*VsUI::CDpiAwareness*クラス。 DpiHelper クラスには、追加の入力パラメーターですが必要とする新しい DpiAwareness と CDpiAwareness クラスが同じ変換ヘルパーを提供します。 変換操作のための参照として使用する UI 要素。 

管理対象の DpiAwareness クラスは、ネイティブ CDpiAwareness クラスは HWND と HMONITOR ヘルパーの中に、WPF のビジュアル、Windows フォーム コントロール、および Win32 Hwnd (IntPtrs の形式での両方)、HMONITORs ヘルパーを提供します。

### <a name="windows-forms-dialogs-windows-or-controls-displayed-in-the-wrong-dpiawarenesscontext"></a>Windows フォーム ダイアログ、windows、または間違った DpiAwarenessContext で表示されるコントロール
Windows (windows の既定の動作) のためのさまざまな DpiAwarenessContext が正常に親子関係後もユーザー拡張性の問題を異なる方法でスケールを異なる DpiAwarenessContext ウィンドウをまだ参照してください可能性があります。 その結果、ユーザーことがありますを参照してください配置/ぼやけてテキストまたはイメージの問題、UI で。

ソリューションでは、アプリケーションのすべてのウィンドウとコントロール用の正しい DpiAwarenessContext スコープを設定します。

### <a name="tlmm-dialogs"></a>TLMM ダイアログ
モーダル ダイアログ ボックスなどの最上位レベルのウィンドウを作成する場合は、スレッドの HWND が作成される前に適切な状態であることを確認してください。 スレッドに配置できるシステムの認識によってネイティブ CDpiScope ヘルパーの使用または DpiAwareness.EnterDpiScope ヘルパーを管理します。 (TLMM は、通常使用非 WPF ダイアログ/windows です。)

### <a name="child-level-mixed-mode-clmm"></a>子レベルの混在モード (CLMM)

既定では、子ウィンドウは、その親として同じ DPI 認識モードを受信します。 ただし、SetThreadDpiHostingBehavior を使用して、このメソッドをオーバーライドし、子ウィンドウを別のスケーリング モードよりも、親またはホストで実行します。


#### <a name="clmm-issues"></a>CLMM の問題
メイン メッセージ ループまたはイベントのチェーンの一部として行われる UI 計算作業のほとんどは、適切な DPI のコンテキストで既に実行する必要があります。 ただしかどうか、座標やサイズの計算の外部で実行これらの主要なワークフロー (などのアイドル時間のタスクでは、または、UI スレッドを関連付けず、DPI の現在のコンテキストできない可能性があります UI の存在を先頭またはミスの問題をサイズ変更に正しかった。 UI の適切な状態にスレッドを配置する作業は通常、問題を修正します。
 
#### <a name="opting-out-of-clmm"></a>CLMM を無効にします。
WPF 以外のツール ウィンドウが PMA を完全にサポートするために移行される場合は、CLMM をオプトアウトする必要があります。 これを行うには、新しいインターフェイスを実装する必要があります。IVsDpiAware します。

C#: 
```cs
[InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
public interface IVsDpiAeware
{
    [ComAliasName("Microsoft.VisualStudio.Shell.Interop.VSDPIMode")]
    uint Mode {get;}
}
```
 
C++: 
```cplusplus
IVsDpiAware : public IUnknown
{
    public:
        HRRESULT STDMETHODCALLTYPE get_Mode(__RCP__out VSDPIMODE *dwMode);
};
```
 

このインターフェイスを実装する最適な場所は、マネージ言語から派生するクラスと同じクラスで*Microsoft.VisualStudio.Shell.ToolWindowPane*します。 C++、このインターフェイスを実装する最適な場所は、同じクラスを実装するには*IVsWindowPane* vsshell.h から。

インターフェイスの Mode プロパティによって返される値は、__VSDPIMODE (およびで uint へのキャストの管理)。

```cs
enum __VSDPIMODE
    {
        VSDM_Unaware    = 0x01,
        VSDM_System     = 0x02,
        VSDM_PerMonitor = 0x03,
    }
```

- ツール ウィンドウは、96 DPI を処理する必要があることを意味に関係なく、Windows がスケールを他のすべての Dpi を処理します。 少し不鮮明されているコンテンツの結果。
- ツール ウィンドウが、プライマリの DPI を処理するシステムの手段では、DPI を表示します。 任意の表示と一致する DPI は、鮮明になりますが、場合は、DPI が異なるか、セッション中の変更、Windows は、スケーリングを処理して、少し不鮮明になります。
- PerMonitor は、すべてのディスプレイ上のすべての Dpi を処理するために必要なツール ウィンドウの DPI が変更されるたびを意味します。

**注**: Visual Studio は、PerMonitor 列挙型の値が DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE_V2 の Windows の値に変換するためにのみ、PerMonitorV2 認識をサポートします。

## <a name="known-issues"></a>既知の問題

### <a name="windows-forms"></a>Windows フォーム

を混合モードの新しいシナリオを最適化するには、は、Windows フォームは、作成する方法コントロールとウィンドウの親が明示的に設定されるたびに変更されました。 以前では、明示的な親なしコントロールは、コントロールまたはウィンドウの作成中に一時的な親として、内部「駐車スペースのウィンドウ」を使用します。 

「駐車スペースのウィンドウ」で、アプリケーションが実行されているプロセスからその DpiAwarenessContext を取得します。 コントロールは、駐車スペースのウィンドウとして同じ DpiAwarenessContext を継承しは、親を再指定元や想定している親をアプリケーション開発者。  これは、目的の親コントロールに作成されるコントロールとして同じ DpiAwarenessContext でない場合に動作しません。

.NET の 4.8 の時点でコントロールまたはウィンドウで、親が明示的に設定されていない場合 Windows フォーム コントロールまたはウィンドウの作成が要求されるスレッドの DpiAwarenessContext に一致するパーキング期間について照会を一時的な親として使用します。 つまり、作成時にコントロールが作成されました DpiAwarenessContext を目的とします。 コントロールまたはウィンドウは、親を再指定に必要な親アプリケーション開発者。
