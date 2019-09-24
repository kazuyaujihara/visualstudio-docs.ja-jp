---
title: ネイティブコードのデバッグ |Microsoft Docs
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
ms.openlocfilehash: 8115d16b64096af343adb918ba4855d9655d4df0
ms.sourcegitcommit: ea182703e922c74725045afc251bcebac305068a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71211145"
---
# <a name="debugging-native-code"></a>ネイティブ コードのデバッグ
ここでは、ネイティブ アプリケーションのデバッグ時に発生する一般的な問題や共通のデバッグ技術について説明します。 ここでは高レベルの手法について説明します。 Visual Studio デバッガーの使用のしくみについては、「[デバッガーの概要](../debugger/debugger-feature-tour.md)」を参照してください)。

## <a name="in-this-section"></a>このセクションの内容
 [方法: 最適化され](../debugger/how-to-debug-optimized-code.md)たコードのデバッグについては、最適化されたコードのデバッグに関するヒント、特に、最適化されていないバージョンのプログラムをデバッグする理由、デバッグ構成とリリース構成の既定の最適化設定、および、最適化されたコードに表示されます (デバッグビルド構成で最適化をオンにします)。

 [DebugBreak と __debugbreak](../debugger/debugbreak-and-debugbreak.md)Win32 `DebugBreak`関数について説明し、Platform SDK のリファレンストピックへのリンクを示します。 また、コンパイラの組み込み関数 `__debugbreak` についても説明します。

 [C/C++アサーション](../debugger/c-cpp-assertions.md)は、アサーションステートメント、そのしくみ、それらを使用する利点 (論理エラーのキャッチ、操作結果のチェック、およびエラー条件のテスト)、と`_DEBUG`の相互作用、およびアサーションの種類について説明します。で[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]サポートされています。

 [方法: 「インラインアセンブリコード](../debugger/how-to-debug-inline-assembly-code.md)のデバッグ」では、[逆アセンブリ] ウィンドウを使用してアセンブリの命令とレジスタウィンドウを表示し、レジスタの内容を表示し、それらのウィンドウに関するトピックへのリンクを示します。

 [MFC のデバッグ技術](../debugger/mfc-debugging-techniques.md)AfxDebugBreak、TRACE マクロ、MFC でのメモリリークの検出、mfc アサーション、MFC デバッグビルドのサイズの縮小など、MFC プログラムのデバッグ手法についてのリンクを示します。

 [CRT のデバッグ技術](../debugger/crt-debugging-techniques.md)CRT デバッグライブラリの使用、レポート用マクロ、malloc と _malloc_dbg の違い、デバッグ用フック関数の記述、CRT デバッグヒープなど、C ランタイムライブラリのデバッグ手法についてのリンクを示します。

 [ネイティブコードのデバッグ](../debugger/debugging-native-code-faqs.md)に関する faqVisual C++プログラムのデバッグに関してよく寄せられる質問への回答を提供します。

 [COM および ActiveX のデバッグ](../debugger/com-and-activex-debugging.md)Com および activex のデバッグに使用できるツールなど、COM および ActiveX アプリケーションのデバッグについて説明します。

 [方法: 挿入され](../debugger/how-to-debug-injected-code.md)たコードのデバッグ属性を使用するコードのデバッグに関するガイダンスを提供します。 ソースの注釈を表示する方法、挿入されたコードを表示する方法、現在の実行ポイントにある逆アセンブリ コードを表示する方法などを説明します。

 [チュートリアル: 並列アプリケーション](../debugger/walkthrough-debugging-a-parallel-application.md)のデバッグ並列**タスク**ウィンドウと**並列スタック**ツールウィンドウを使用して並列アプリケーションをデバッグする方法について説明します。

## <a name="related-sections"></a>関連項目
 [ビジュアルC++ ](../debugger/debugging-preparation-visual-cpp-project-types.md)プロジェクトの種類 visual C++プロジェクトテンプレートによって作成されたネイティブプロジェクトの種類をデバッグする方法について説明するトピックへのリンクを提供します。

 [DLL プロジェクトのデバッグ](../debugger/debugging-dll-projects.md)ネイティブ Dll とマネージ Dll をデバッグする方法について説明します。

 [最初にデバッガーを確認する](../debugger/debugger-feature-tour.md)デバッグドキュメントのより大きなセクションへのリンクを示します。 デバッガーの新機能、設定と準備、ブレークポイント、例外の処理、エディット コンティニュ、マネージド コードのデバッグ、ネイティブ コードのデバッグ、SQL のデバッグ、ユーザー インターフェイス リファレンスなどの情報へのリンクを提供します。

## <a name="see-also"></a>関連項目

- [デバッガーのセキュリティ](../debugger/debugger-security.md)
- [Visual Studio でのデバッグ](../debugger/index.yml)