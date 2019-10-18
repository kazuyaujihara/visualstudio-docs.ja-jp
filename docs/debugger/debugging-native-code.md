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
ms.openlocfilehash: e51918122834dd6b50952b9cc81a1d24a6477dd0
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72431770"
---
# <a name="debugging-native-code"></a>ネイティブ コードのデバッグ
ここでは、ネイティブ アプリケーションのデバッグ時に発生する一般的な問題や共通のデバッグ技術について説明します。 ここでは高レベルの手法について説明します。 Visual Studio デバッガーの使用のしくみについては、「[デバッガーの概要](../debugger/debugger-feature-tour.md)」を参照してください)。

## <a name="in-this-section"></a>このセクションの内容
 [方法: 最適化](../debugger/how-to-debug-optimized-code.md)されたコードをデバッグする最適化されたコードのデバッグに関するヒントを提供します。具体的には、最適化されていないバージョンのプログラムをデバッグする理由、デバッグ構成とリリース構成の既定の最適化設定、最適化されたコードにのみ表示されるバグを検出するためのヒント (オンにするデバッグビルド構成での最適化。

 [DebugBreak と __debugbreak](../debugger/debugbreak-and-debugbreak.md)Win32 `DebugBreak` 関数について説明し、Platform SDK のリファレンストピックへのリンクを示します。 また、コンパイラの組み込み関数 `__debugbreak` についても説明します。

 [C/C++アサーション](../debugger/c-cpp-assertions.md)アサーションステートメント、そのしくみ、それらを使用する利点 (論理エラーのキャッチ、操作結果のチェック、およびエラー条件のテスト)、`_DEBUG` との相互作用、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] でサポートされているアサーションの種類について説明します。

 [方法: インラインアセンブラーコードをデバッグする](../debugger/how-to-debug-inline-assembly-code.md)[逆アセンブリ] ウィンドウを使用してアセンブリの命令とレジスタウィンドウを表示し、レジスタの内容を表示し、それらのウィンドウに関するトピックへのリンクを提供する簡単な手順を説明します。

 [MFC のデバッグ技術](../debugger/mfc-debugging-techniques.md)AfxDebugBreak、TRACE マクロ、MFC でのメモリリークの検出、mfc アサーション、MFC デバッグビルドのサイズの縮小など、MFC プログラムのデバッグ手法についてのリンクを示します。

 [CRT のデバッグ技術](../debugger/crt-debugging-techniques.md)CRT デバッグライブラリの使用、レポート用マクロ、malloc と _malloc_dbg の違い、デバッグ用フック関数の記述、CRT デバッグヒープなど、C ランタイムライブラリのデバッグ手法についてのリンクを示します。

 [ネイティブコードのデバッグ](../debugger/debugging-native-code-faqs.md)に関する faqプログラムのデバッグC++に関してよく寄せられる質問への回答を提供します。

 [COM および ActiveX のデバッグ](../debugger/com-and-activex-debugging.md)Com および activex のデバッグに使用できるツールなど、COM および ActiveX アプリケーションのデバッグについて説明します。

 [方法: 挿入されるコードをデバッグする](../debugger/how-to-debug-injected-code.md)属性を使用するコードのデバッグに関するガイダンスを提供します。 ソースの注釈を表示する方法、挿入されたコードを表示する方法、現在の実行ポイントにある逆アセンブリ コードを表示する方法などを説明します。

 [チュートリアル: 並列アプリケーションのデバッグ](../debugger/walkthrough-debugging-a-parallel-application.md)並列**タスク**ウィンドウと**並列スタック**ツールウィンドウを使用して並列アプリケーションをデバッグする方法について説明します。

## <a name="related-sections"></a>関連項目
 [プロジェクトのデバッグC++の準備](../debugger/debugging-preparation-visual-cpp-project-types.md)プロジェクトテンプレートによってC++作成されたネイティブプロジェクトの種類をデバッグする方法について説明するトピックへのリンクを提供します。

 [DLL プロジェクトのデバッグ](../debugger/debugging-dll-projects.md)ネイティブ Dll とマネージ Dll をデバッグする方法について説明します。

 [最初にデバッガーを確認する](../debugger/debugger-feature-tour.md)デバッグドキュメントのより大きなセクションへのリンクを示します。 デバッガーの新機能、設定と準備、ブレークポイント、例外の処理、エディット コンティニュ、マネージド コードのデバッグ、ネイティブ コードのデバッグ、SQL のデバッグ、ユーザー インターフェイス リファレンスなどの情報へのリンクを提供します。

## <a name="see-also"></a>参照

- [デバッガーのセキュリティ](../debugger/debugger-security.md)
- [Visual Studio でのデバッグ](../debugger/index.yml)