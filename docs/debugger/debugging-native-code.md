---
title: ネイティブ コードのデバッグ |Microsoft Docs
ms.date: 04/11/2017
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging native code
- debugging [C++], native code
- debugging [Visual Studio], native code
- native code, debugging
ms.assetid: d94eee90-7e0d-4cac-88c1-9831030daa5e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 5a7cf0b150c45037941010bf7e611f4bc21252c7
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "57870416"
---
# <a name="debugging-native-code"></a>ネイティブ コードのデバッグ
ここでは、ネイティブ アプリケーションのデバッグ時に発生する一般的な問題や共通のデバッグ技術について説明します。 ここでは高レベルの手法について説明します。 Visual Studio デバッガーの使用のしくみを参照してください。[デバッガーでのはじめ](../debugger/debugger-feature-tour.md))。

## <a name="in-this-section"></a>このセクションの内容
 [方法: 最適化されたコードのデバッグ](../debugger/how-to-debug-optimized-code.md)デバッグとリリースの構成の既定の最適化の設定、プログラムの最適化されていないバージョンをデバッグするため、具体的には、最適化されたコードをデバッグするためのヒントを紹介し、バグの検索のヒント(デバッグ ビルド構成での最適化の有効化) 最適化されたコードにのみ表示されます。

 [DebugBreak と _ _debugbreak](../debugger/debugbreak-and-debugbreak.md) Win32 について説明します`DebugBreak`関数し、プラットフォーム SDK のリファレンス トピックへのリンクを提供します。 また、コンパイラの組み込み関数 `__debugbreak` についても説明します。

 [C/C++ アサーション](../debugger/c-cpp-assertions.md)アサート ステートメント、そのしくみ、(論理エラーのキャッチ、操作の結果を確認して、エラー条件のテスト)、それらを使用する利点について説明しますとの相互作用`_DEBUG`との種類サポートされるアサーション[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]します。

 [方法: インライン アセンブラー コードをデバッグ](../debugger/how-to-debug-inline-assembly-code.md)レジスタの内容を逆アセンブル ウィンドウを使用して表示するには、アセンブリ命令およびレジスタ ウィンドウを表示する簡単な指示を提供し、これらのウィンドウに関するトピックへのリンクを提供します。

 [MFC のデバッグ技術](../debugger/mfc-debugging-techniques.md)手法など、MFC プログラムをデバッグするリンクを: mfc では、MFC アサーション、リークを afxDebugBreak、TRACE マクロは、メモリを検出して、ビルド MFC デバッグのサイズを小さきます。

 [CRT のデバッグ技術](../debugger/crt-debugging-techniques.md)CRT デバッグのライブラリ、レポート用マクロの使用を含む、C ランタイム ライブラリのデバッグ手法へのリンクと、malloc と _malloc_dbg、デバッグ用フック関数、および CRT デバッグ ヒープの作成の間の相違点します。

 [よく寄せられる質問がネイティブ コードをデバッグ](../debugger/debugging-native-code-faqs.md)Visual C プログラムのデバッグに関してよく寄せられる質問に対する回答を提供します。

 [COM および ActiveX のデバッグ](../debugger/com-and-activex-debugging.md)COM の使用できるツールなど、COM および ActiveX アプリケーションのデバッグと ActiveX のデバッグについて説明します。

 [方法: 挿入されたコードをデバッグ](../debugger/how-to-debug-injected-code.md)属性を使用するコードのデバッグに関するガイダンスを示します。 ソースの注釈を表示する方法、挿入されたコードを表示する方法、現在の実行ポイントにある逆アセンブリ コードを表示する方法などを説明します。

 [チュートリアル: 並行アプリケーションのデバッグ](../debugger/walkthrough-debugging-a-parallel-application.md)を使用する方法について説明します、**並列タスク**と**並列スタック**ツール ウィンドウを並行アプリケーションをデバッグします。

## <a name="related-sections"></a>関連項目
 [C++ プロジェクトのビジュアルの種類](../debugger/debugging-preparation-visual-cpp-project-types.md)Visual C プロジェクト テンプレートで作成されたネイティブ プロジェクトをデバッグする方法を説明するトピックへのリンクを提供します。

 [DLL プロジェクトのデバッグ](../debugger/debugging-dll-projects.md)ネイティブおよびマネージ Dll をデバッグする方法について説明します。

 [デバッガーでのはじめ](../debugger/debugger-feature-tour.md)デバッグ ドキュメントの大きなセクションへのリンクを提供します。 デバッガーの新機能、設定と準備、ブレークポイント、例外の処理、エディット コンティニュ、マネージド コードのデバッグ、ネイティブ コードのデバッグ、SQL のデバッグ、ユーザー インターフェイス リファレンスなどの情報へのリンクを提供します。

## <a name="see-also"></a>関連項目

- [デバッガーのセキュリティ](../debugger/debugger-security.md)
- [Visual Studio でのデバッグ](../debugger/index.md)