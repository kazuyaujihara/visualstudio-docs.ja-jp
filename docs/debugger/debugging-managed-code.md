---
title: マネージ コードのデバッグ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging managed code
- debugging ASP.NET Web applications, managed code
- managed code, debugging
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 14dc53413f646718b85ec9ea43d968dc9f64a96f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719317"
---
# <a name="debugging-managed-code"></a>マネージド コードのデバッグ

ここでは、マネージド アプリケーションに共通するデバッグの問題と手法について説明します。マネージド アプリケーションは、Visual Basic、C#、C++ など、共通言語ランタイムをターゲットにした言語で記述されたアプリケーションです。 ここでは、高度な手法について説明します。 [デバッガーでのはじめに](../debugger/debugger-feature-tour.md)

## <a name="in-this-section"></a>このセクションの内容

[出力ウィンドウの診断メッセージ](../debugger/diagnostic-messages-in-the-output-window.md)方法について説明します、<xref:System.Diagnostics.Debug>と<xref:System.Diagnostics.Trace>クラスを実行時のメッセージを記述できます、**出力**ウィンドウ。 Debug クラスと Trace クラスに含まれている出力メソッドを使用すると、実行の中断を伴わない情報出力、および指定した条件が満たされなかった場合に実行の中断を伴う情報出力ができます。

[マネージ コードでアサーション](../debugger/assertions-in-managed-code.md)への引数として指定した条件をテストするマネージ コードでアサーションをについて説明します。`Assert`メソッド。 ここでは、サンプル コード、<xref:System.Diagnostics.Debug> クラスと <xref:System.Diagnostics.Trace> クラスのメソッドの使用に関する情報、デバッグ バージョンとリリース バージョンのコードの注意事項、副作用、アサートの引数、アサートの動作のカスタマイズ、および構成ファイルについても説明します。

[Visual Basic でのステートメントを停止](../debugger/stop-statements-in-visual-basic.md)方法について説明します、`Stop`ステートメントで、ブレークポイントの設定の代替を提供します。 サンプル コードを示し、`Stop` ステートメントと `End` ステートメントの比較、および `Stop` ステートメントと `Assert` ステートメントの比較を行います。

[チュートリアル: Windows フォームのデバッグ](../debugger/walkthrough-debugging-a-windows-form.md)Windows フォームを作成すると、そのフォームをデバッグする手順について説明します。 マネージド Windows アプリケーションの標準コンポーネントである Windows フォームは、最も一般的なマネージド アプリケーションの 1 つです。 このチュートリアルでは Visual C# と Visual Basic を使用しますが、C++ を使って Windows フォームを作成する場合と方法は似ています。

[OnStart メソッドをデバッグ](../debugger/how-to-debug-the-onstart-method.md)をデバッグすることを許可するコード例を示します、`OnStart`マネージ Windows サービスのメソッド。 Windows サービスの `OnStart` メソッドをデバッグするには、サービスをシミュレートする数行のコードを追加する必要があります。

[混合モード デバッグ](../debugger/debugging-mixed-mode-applications.md)混合モード アプリケーションのデバッグについて説明します。 これは、ネイティブ コードとマネージド コードを組み合わせたアプリケーションです。

[エラー: システムのカーネル デバッガーが有効になっているため、がデバッグできません](../debugger/error-debugging-isn-t-possible-because-a-kernel-debugger-is-enabled-on-the-system.md)でマネージ コードをデバッグしようとする場合に発生するエラー メッセージについて説明します、 [!INCLUDE[win7](../debugger/includes/win7_md.md)]、 [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)]、 [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)]、 [!INCLUDE[Win2kFamily](../code-quality/includes/win2kfamily_md.md)]、または Windows NT システムですが、デバッグ モードで開始されました。

[JIT の最適化とデバッグ](../debugger/jit-optimization-and-debugging.md)デバッグに JIT 最適化の効果について説明します。

[LINQ および DLINQ のデバッグ](../debugger/debugging-linq.md)を LINQ クエリをデバッグする方法について説明します。

[チュートリアル: 並行アプリケーションのデバッグ](../debugger/walkthrough-debugging-a-parallel-application.md)を使用する方法について説明します、**並列タスク**と**並列スタック**ツール ウィンドウを並行アプリケーションをデバッグします。

## <a name="related-sections"></a>関連項目

[IntelliTrace](../debugger/intellitrace.md) IntelliTrace を使用したアプリの実行履歴の記録による高速かつ簡単にバグを発見します。 記録されたイベントと呼び出しを前後にステップ実行して重要な時点でのアプリの状態を調べます。 多くのブレークポイントを設定することも、アプリを頻繁に再起動することもなく、コードをデバッグします。 Visual Studio Enterprise が必要です。

[トレースとアプリケーションのインストルメント化](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)トレースの実行は、インストルメント化中に、アプリケーションの実行を監視する方法について説明していますが、コードの戦略的な位置にトレース ステートメントを配置することです。 ここでは、ステートメントのインストルメンテーションとトレース、トレース スイッチ、トレース リスナー、アプリケーション コードのトレース、アプリケーション コードへのトレース ステートメントの追加、<xref:System.Diagnostics.Debug> と <xref:System.Diagnostics.Trace> を使った条件付きコンパイルの説明へのリンクを提供します。

[/ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute)を追加するリンカー オプションについて説明します<xref:System.Diagnostics.DebuggableAttribute>C++ で記述されたコードにします。 この属性は、C++ によるアタッチなどのデバッグ機能を使用するときに必要です。

[Windows サービス アプリケーションのデバッグ](/dotnet/framework/windows-services/how-to-debug-windows-service-applications)Windows サービス アプリケーションのデバッグのセットアップなど、プロセスへのアタッチ、サービスのコードのデバッグに関する考慮事項を提供します`OnStart`メソッドと、メインのコード。メソッド、ブレークポイントの設定、および開始するには、サービス コントロール マネージャーを使用して、停止、一時停止、およびサービスを続行します。

[デバッグとプロファイリング](/dotnet/framework/debug-trace-profile/index).NET Framework アプリケーションのデバッグと構成要件について説明します。

[スクリプトと Web アプリケーションのデバッグ](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications)共通の問題と手法のスクリプトと Web アプリケーションをデバッグするときに発生する可能性をデバッグする方法について説明します。

[Visual Studio 2015 のデバッガーの新](../debugger/what-s-new-for-the-debugger-in-visual-studio.md)のこのリリースで追加された新しいのデバッグ機能の説明[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]します。

[ホーム ページのデバッグ](../debugger/debugger-feature-tour.md)デバッグ ドキュメントの大きなセクションへのリンクを提供します。 これらのリンクでは、デバッガーの新機能、設定と準備、ブレークポイント、例外処理、エディット コンティニュ、マネージド コードのデバッグ、Visual C++ プロジェクトのデバッグ、COM および ActiveX のデバッグ、DLL のデバッグ、SQL のデバッグ、ユーザー インターフェイス リファレンスなどの情報が示されます。

## <a name="see-also"></a>関連項目

[チュートリアル: カスタム Windows フォーム コントロールのデバッグ デザイン時に](/dotnet/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time)
[デバッガーのセキュリティ](../debugger/debugger-security.md)
[Visual Studio でのデバッグ](../debugger/index.md)
 [デバッガーでのはじめ](../debugger/debugger-feature-tour.md)