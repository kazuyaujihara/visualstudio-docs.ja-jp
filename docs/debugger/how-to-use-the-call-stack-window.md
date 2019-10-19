---
title: デバッガーで呼び出し履歴を表示する |Microsoft Docs
ms.custom: seodec18
ms.date: 10/29/2018
ms.topic: conceptual
f1_keywords:
- vs.debug.callstack
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
- aspx
helpviewer_keywords:
- threading [Visual Studio], displaying calls to or from
- functions [debugger], viewing code on call stack
- disassembly code
- breakpoints, Call Stack window
- debugging [Visual Studio], switching to another stack frame
- debugging [Visual Studio], Call Stack window
- Call Stack window, viewing source code for functions on the call stack
- stack, switching stack frames
- Call Stack window, viewing disassembly code for functions on the call stack
ms.assetid: 5154a2a1-4729-4dbb-b675-db611a72a731
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 21573f1f8bd49782739027f7dfc2034bb7501a2f
ms.sourcegitcommit: 08c144d290da373df841f04fc799e3133540a541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72535978"
---
# <a name="view-the-call-stack-and-use-the-call-stack-window-in-the-debugger"></a>呼び出し履歴を表示し、デバッガーで [呼び出し履歴] ウィンドウを使用する

**[呼び出し履歴]** ウィンドウを使用すると、現在呼び出し履歴にある関数呼び出しやプロシージャ呼び出しを表示できます。 **[呼び出し履歴]** ウィンドウには、メソッドおよび関数が呼び出されている順番が表示されます。 呼び出し履歴は、アプリの実行フローを調査して理解するのに優れた方法です。

コールスタックの一部で[デバッグシンボル](#bkmk_symbols)を使用できない場合 **、呼び出し履歴ウィンドウで**は、呼び出し履歴のその部分に関する正しい情報を表示できない可能性があります。代わりに、を表示します。

`[Frames below may be incorrect and/or missing, no symbols loaded for name.dll]`

> [!NOTE]
> **[呼び出し履歴]** ウィンドウは、Eclipse のような一部の IDE におけるデバッグ パースペクティブに似ています。

> [!NOTE]
> 実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ここで説明する内容と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。  「[設定のリセット](../ide/environment-settings.md#reset-settings)」を参照してください。

## <a name="view-the-call-stack-while-in-the-debugger"></a>デバッガーでの呼び出し履歴の表示

- デバッグ中に、 **[デバッグ]** メニューの **[Windows > の呼び出し履歴]** をクリックします。

  ![呼び出し履歴ウィンドウ](../debugger/media/dbg_basics_callstack_window.png "CallStackWindow")

黄色の矢印は、現在、実行ポインターが存在するスタック フレームを示します。 既定では、このスタックフレームの情報は、ソース、**ローカル**、**自動変数**、**ウォッチ**、および **逆アセンブリ** ウィンドウに表示されます。 デバッガーコンテキストをスタック上の別のフレームに変更するには、[別のスタックフレームに切り替え](#bkmk_switch)ます。

## <a name="display-non-user-code-in-the-call-stack-window"></a>[呼び出し履歴] ウィンドウに非ユーザーコードを表示する

- **[呼び出し履歴]** ウィンドウを右クリックし、 **[外部コードの表示]** をクリックします。

非ユーザーコードは、[マイコードのみ](../debugger/just-my-code.md)が有効になっている場合に表示されないコードです。 マネージコードでは、非ユーザーコードフレームは既定で非表示になっています。 非ユーザーコードフレームの代わりに、次の表記が表示されます。

`[<External Code>]`

## <a name="bkmk_switch"></a>別のスタックフレームに切り替える (デバッガーコンテキストを変更する)

1. **[呼び出し履歴]** ウィンドウで、表示するコードとデータが含まれているスタックフレームを右クリックします。

    または、 **[呼び出し履歴]** ウィンドウ内のフレームをダブルクリックして、そのフレームに切り替えることもできます。

2. **[フレームに切り替え]** をクリックします。

     選択したスタックフレームの横に、尾の付いた緑色の矢印が表示されます。 実行ポインターは、黄色の矢印でマークされた元のフレームに置かれたままです。 **[デバッグ]** メニューの **[ステップ]** または **[続行]** をクリックすると、選択したフレームではなく、元のフレームで実行が継続されます。

## <a name="view-the-source-code-for-a-function-on-the-call-stack"></a>呼び出し履歴上の関数のソースコードを表示する

- **[呼び出し履歴]** ウィンドウで、ソース コードを表示する関数を右クリックし、 **[ソース コードへ移動]** をクリックします。

## <a name="run-to-a-specific-function-from-the-call-stack-window"></a>[呼び出し履歴] ウィンドウから特定の関数まで実行する

- **[呼び出し履歴]** ウィンドウで関数を選択し、右クリックして、 **[カーソル行の前まで実行]** をクリックします。

## <a name="set-a-breakpoint-on-the-exit-point-of-a-function-call"></a>関数呼び出しの終了ポイントにブレークポイントを設定する

- 「[呼び出し履歴関数にブレークポイントを設定する](../debugger/using-breakpoints.md#BKMK_Set_a_breakpoint_from_debugger_windows)」を参照してください。

## <a name="display-calls-to-or-from-another-thread"></a>別のスレッドの呼び出しを表示する

- **[呼び出し履歴]** ウィンドウを右クリックし、 **[他のスレッドの呼び出しを含む]** をクリックします。

## <a name="visually-trace-the-call-stack"></a>呼び出し履歴を視覚的にトレースする

Visual Studio Enterprise (のみ) では、デバッグ中に呼び出し履歴のコードマップを表示できます。

- **[呼び出し履歴]** ウィンドウでショートカット メニューを開きます。 **[コードマップの呼び出し履歴を表示]** をクリックします (**Ctrl**  + **Shift**  +  **`** )。

    詳細については、「[デバッグ中の呼び出し履歴のメソッドのマップ](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)」を参照してください。

![コードマップに呼び出し履歴を表示する](../debugger/media/dbg_basics_show_call_stack_on_code_map.gif "ShowCallStackOnCodeMap")

## <a name="view-the-disassembly-code-for-a-function-on-the-call-stack-c-c-visual-basic-f"></a>呼び出し履歴上の関数の逆アセンブリコードを表示するC#( C++、、Visual Basic F#、)

- **[呼び出し履歴]** ウィンドウで、逆アセンブリ コードを表示する関数を右クリックし、 **[逆アセンブルを表示]** をクリックします。

## <a name="change-the-optional-information-displayed"></a>表示されるオプションの情報を変更する

- **[呼び出し履歴]** ウィンドウを右クリックし、 **[表示]** を設定またはオフにして、 **>** _する情報_を \< します。

## <a name="bkmk_symbols"></a>モジュール (C#、 C++、Visual Basic、 F#) のシンボルを読み込みます

**[呼び出し履歴]** ウィンドウで、シンボルがまだ読み込まれていないコードに対してデバッグ シンボルを読み込むことができます。 これらのシンボルには、Microsoft パブリックシンボルサーバーからダウンロードされた .NET またはシステムシンボル、またはデバッグしているコンピューター上のシンボルパスのシンボルを使用できます。

[シンボル (.pdb) ファイルとソース ファイルの指定](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)に関する記事をご覧ください。

### <a name="to-load-symbols"></a>シンボルを読み込むには

1. **[呼び出し履歴]** ウィンドウで、シンボルが読み込まれていないスタックフレームを右クリックします。 フレームが淡色表示されます。

2. **[シンボルの読み込み]** をポイントし、 **[Microsoft シンボルサーバー]** (使用可能な場合) を選択するか、シンボルパスを参照します。

### <a name="to-set-the-symbol-path"></a>シンボル パスを設定するには

1. **[呼び出し履歴]** ウィンドウで、ショートカット メニューの **[シンボルの設定]** をクリックします。

     **[オプション]** ダイアログ ボックスが表示され、 **[シンボル]** ページが表示されます。

2. **シンボル設定**を選択します。

3. **[オプション]** ダイアログ ボックスで、フォルダー アイコンをクリックします。

     **[シンボル ファイル (.pdb) の場所]** ボックスにカーソルが表示されます。

4. デバッグするコンピューター上のシンボルの場所のディレクトリパス名を入力します。 ローカルおよびリモートデバッグの場合、これはローカルコンピューター上のパスです。

5. **[OK]** を選択して **[オプション]** ダイアログボックスを閉じます。

## <a name="see-also"></a>関連項目

- [[呼び出し履歴] ウィンドウの混合コードと不足情報](../debugger/mixed-code-and-missing-information-in-the-call-stack-window.md)
- [デバッガーでのデータ表示](../debugger/viewing-data-in-the-debugger.md)
- [シンボル (.pdb) とソース ファイルの指定](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)
- [ブレークポイントの使用](../debugger/using-breakpoints.md)