---
title: マルチスレッド アプリケーションのデバッグ
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.gputthreads
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], high-performance computing
- debugging [Visual Studio], multithreaded
- multithreaded debugging
- high-performance debugging
ms.assetid: 9d175bc2-1d95-4c47-9bc3-9755af968a9c
caps.latest.revision: 28
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8315a797aec5fcedbf33df6ca96f41879b57d971
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60054301"
---
# <a name="debug-multithreaded-applications-in-visual-studio"></a>マルチスレッド アプリケーションのデバッグ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

スレッドは、オペレーティング システムでプロセッサ時間を割り当てる命令のシーケンスです。 オペレーティング システムで実行されているプロセスは、いずれも 1 つ以上のスレッドで構成されます。 複数のスレッドで構成されるプロセスをマルチスレッド プロセスといいます。

 複数のプロセッサ、マルチコア プロセッサ、またはハイパースレッディング プロセッサを搭載したコンピューターでは、同時に複数のスレッドを実行できます。 複数のスレッドを同時に実行すると、プログラムのパフォーマンスは大幅に向上しますが、複数のスレッドを追跡する必要があるため、デバッグは難しくなります。

 また、マルチスレッドには新しい種類の潜在的な問題が伴います。 たとえば、複数のスレッドが同じリソースにアクセスする必要があり、一度に 1 つのスレッドだけがそのリソースに安全にアクセスできるということがよくあります。 一度に 1 つのスレッドだけがリソースにアクセスできるようにするには、相互排他を適用する必要があります。 相互排他が正しく実行しない場合は作成できます、*デッドロック*条件で実行できるスレッドはありません。 デッドロックは、デバッグが特に困難な問題の 1 つです。

 Visual Studio では、**スレッド**ウィンドウ、GPU スレッド ウィンドウ、並列ウォッチ ウィンドウ、およびマルチ スレッド デバッグが容易にする機能。 スレッド機能の詳細について確認するには、チュートリアルを完了することをお勧めします。 「[チュートリアル:マルチ スレッド アプリケーションのデバッグ](../debugger/walkthrough-debugging-a-multithreaded-application.md)と[チュートリアル。C++ AMP アプリケーションのデバッグ](http://msdn.microsoft.com/library/40e92ecc-f6ba-411c-960c-b3047b854fb5)します。

 Visual Studio には、強力なブレークポイントとトレースポイントも用意されており、マルチスレッド アプリケーションのデバッグに役立ちます。 ブレークポイント フィルターを使用すると、個々のスレッドにブレークポイントを配置できます。 参照してください[ブレークポイントの使用](../debugger/using-breakpoints.md)

 ユーザー インターフェイスを含むマルチスレッド アプリケーションは、特にデバッグが困難になることがあります。 その場合には、アプリケーションを別のコンピューターで実行し、リモート デバッグを使用することを検討してください。 詳しくは、次を参照してください。[リモート デバッグ](../debugger/remote-debugging.md)します。

## <a name="in-this-section"></a>このセクションの内容
 [スレッドとプロセス](../debugger/debug-threads-and-processes.md)スレッドとプロセスのデバッグの基礎を説明します。

 [複数のプロセスをデバッグ](../debugger/debug-multiple-processes.md)複数プロセスをデバッグする方法について説明します。

 [方法: [スレッド] ウィンドウを使用して、](../debugger/how-to-use-the-threads-window.md)でスレッドをデバッグするための便利なプロシージャ、**スレッド**ウィンドウ。

 [方法: 別のスレッド デバッグ中に切り替える](../debugger/how-to-switch-to-another-thread-while-debugging.md)デバッグ コンテキストを別のスレッドに切り替える 3 つの方法です。

 [方法: フラグとスレッドのフラグを解除](../debugger/how-to-flag-and-unflag-threads.md)デバッグ中に、特に注目するスレッドをマークまたはフラグ。

 [方法: ネイティブ コードのスレッド名を設定](../debugger/how-to-set-a-thread-name-in-native-code.md)、スレッドに表示される名前を付けて、**スレッド**ウィンドウ。

 [方法: マネージ コードのスレッド名を設定](../debugger/how-to-set-a-thread-name-in-managed-code.md)、スレッドに表示される名前を付けて、**スレッド**ウィンドウ。

 [チュートリアル: マルチ スレッド アプリケーションのデバッグ](../debugger/walkthrough-debugging-a-multithreaded-application.md)します。
[!INCLUDE[vs_orcas_long](../includes/vs-orcas-long-md.md)] の方法に重点を置いてスレッドのデバッグ機能を紹介するガイド ツアーです。

 [方法: 高パフォーマンス クラスター上でデバッグ](../debugger/how-to-debug-on-a-high-performance-cluster.md)を高パフォーマンス クラスター上で実行するアプリケーションをデバッグする方法。

 [ネイティブ コードでスレッドをデバッグするためのヒント](../debugger/tips-for-debugging-threads-in-native-code.md)簡単な手法については、ネイティブ スレッドのデバッグに役立ちます。

 [[タスク] ウィンドウを使用して](../debugger/using-the-tasks-window.md)それらの状態とその他の有益な情報を含め、すべてのマネージまたはネイティブのタスク オブジェクトの一覧が表示されます。

 [並列スタック ウィンドウを使用して](../debugger/using-the-parallel-stacks-window.md)示します呼び出しを複数のスレッド (またはタスク) の 1 つのビューとそのスタックもスレッド (またはタスク) の間で共通のスタック セグメントを連結します。

 [チュートリアル: 並列アプリケーションのデバッグ](../debugger/walkthrough-debugging-a-parallel-application.md)並列タスク ウィンドウと並列スタック ウィンドウを使用する方法を示すチュートリアルです。

 [方法: 並列ウォッチ ウィンドウを使用して、](../debugger/how-to-use-the-parallel-watch-window.md)複数のスレッドの値と式を検査します。

 [方法: GPU スレッド ウィンドウを使用して、](../debugger/how-to-use-the-gpu-threads-window.md)の確認とデバッグ中に GPU 上で実行されているスレッドで作業します。

## <a name="related-sections"></a>関連項目

[ブレークポイントの使用](../debugger/using-breakpoints.md)
- 個々のスレッドにブレークポイントを配置する場合にブレークポイント フィルターを使用する方法について説明します。

- トレースポイントを使用すると、プログラムの実行を中断なしでトレースできます。 この方法はデッドロックなどの問題を調べる場合に役立ちます。

  [スレッド処理](http://msdn.microsoft.com/library/7b46a7d9-c6f1-46d1-a947-ae97471bba87)スレッド処理の概念で[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]プログラミングでは、例のコードを含みます。

  [コンポーネントのマルチ スレッド](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)を使用する方法でのマルチ スレッド[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]コンポーネント。

  [古いコード (Visual C) のためのマルチ スレッド サポート](http://msdn.microsoft.com/library/24425b1f-5031-4c6b-aac7-017115a40e7c)MFC を使用する C++ プログラマのための概念とコード例のスレッドを処理します。

## <a name="see-also"></a>関連項目
 [スレッドとプロセス](../debugger/debug-threads-and-processes.md)[リモート デバッグ](../debugger/remote-debugging.md)
