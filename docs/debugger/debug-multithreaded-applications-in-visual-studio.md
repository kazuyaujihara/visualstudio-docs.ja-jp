---
title: マルチスレッドアプリケーションのデバッグ |Microsoft Docs
ms.custom: seodec18
ms.date: 11/06/2018
ms.topic: conceptual
f1_keywords:
- vs.debug.gputthreads
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], high-performance computing
- debugging [Visual Studio], multithreaded
- multithreaded debugging
- high-performance debugging
ms.assetid: 9d175bc2-1d95-4c47-9bc3-9755af968a9c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 668e95c340348eeb1fa509622aa44d99b65b6efc
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72431810"
---
# <a name="debug-multithreaded-applications-in-visual-studio"></a>Visual Studio でマルチスレッド アプリケーションをデバッグする
スレッドは、オペレーティングシステムによってプロセッサ時間が付与される命令のシーケンスです。 オペレーティング システムで実行されているプロセスは、いずれも 1 つ以上のスレッドで構成されます。 複数のスレッドで構成されるプロセスをマルチスレッド プロセスといいます。

複数のプロセッサを搭載したコンピューター、マルチコアプロセッサ、またはハイパースレッディングプロセスでは、複数のスレッドを同時に実行できます。 多くのスレッドを使用する並列処理では、プログラムのパフォーマンスを大幅に向上させることができますが、多くのスレッドを追跡しているため、デバッグが困難になる場合もあります。

マルチスレッドでは、新しい種類の潜在的なバグを導入できます。 たとえば、2つ以上のスレッドが同じリソースにアクセスすることが必要になる場合がありますが、リソースに安全にアクセスできるスレッドは一度に1つだけです。 任意の時点で1つのスレッドだけがリソースにアクセスするようにするには、相互排他の何らかの形式が必要です。 相互排他が正しく実装されていない場合は、スレッドが実行されない*デッドロック*状態が発生する可能性があります。 多くの場合、デッドロックはデバッグに困難な問題です。

## <a name="tools-for-debugging-multithreaded-apps"></a>マルチスレッドアプリをデバッグするためのツール

Visual Studio には、マルチスレッドアプリのデバッグに使用できるさまざまなツールが用意されています。

- スレッドの場合、スレッドをデバッグするための主要なツールは、 **[スレッド]** ウィンドウ、ソースウィンドウのスレッドマーカー、 **[並列スタック]** ウィンドウ、 **[並列ウォッチ]** ウィンドウ、および **[デバッグの場所]** ツールバーです。 **[スレッド]** ウィンドウと **[デバッグの場所]** ツールバーの詳細については、「[チュートリアル: [スレッド] ウィンドウを使用したデバッグ](../debugger/how-to-use-the-threads-window.md)」を参照してください。 **並列スタック**と**並列ウォッチ**ウィンドウの使用方法については、「[マルチスレッドアプリケーションのデバッグの概要](../debugger/get-started-debugging-multithreaded-apps.md)」を参照してください。 どちらのトピックも、スレッドマーカーの使用方法を示しています。

- [タスク並列ライブラリ (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl)または[同時実行ランタイム](/cpp/parallel/concrt/concurrency-runtime/)を使用するコードの場合、デバッグ用の主要なツールは、 **[並列スタック]** ウィンドウ、 **[並列ウォッチ]** ウィンドウ、および **[タスク]** ウィンドウです。このウィンドウでもサポートされます。Java. 作業を開始するには、「[チュートリアル: 並列アプリケーションのデバッグ](../debugger/walkthrough-debugging-a-parallel-application.md)」および「[チュートリアル: AMP アプリケーションのC++デバッグ](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application)」を参照してください。

- GPU 上のスレッドのデバッグの場合、プライマリツールは **[Gpu スレッド]** ウィンドウです。 「[方法: GPU スレッドウィンドウを使用する」を](../debugger/how-to-use-the-gpu-threads-window.md)参照してください。

- プロセスの主要なツールは、 **[プロセスにアタッチ]** ダイアログボックス、 **[プロセス]** ウィンドウ、および **[デバッグの場所]** ツールバーです。

Visual Studio には、強力なブレークポイントとトレースポイントも用意されています。これは、マルチスレッドアプリケーションをデバッグするときに便利です。 ブレークポイントの条件とフィルターを使用して、個々のスレッドにブレークポイントを設定します。 トレースポイントを使用すると、デッドロックなどの問題を調査するために、プログラムの実行を中断することなくトレースできます。 詳細については、「[ブレークポイントアクションとトレース](../debugger/using-breakpoints.md#BKMK_Print_to_the_Output_window_with_tracepoints)ポイント」を参照してください。

ユーザー インターフェイスを含むマルチスレッド アプリケーションは、特にデバッグが困難になることがあります。 アプリケーションを2台目のコンピューターで実行し、リモートデバッグを使用することを検討してください。 詳細については、「[リモートデバッグ](../debugger/remote-debugging.md)」を参照してください。

## <a name="articles-about-debugging-multithreaded-apps"></a>マルチスレッドアプリのデバッグに関する記事

 [マルチスレッドアプリケーションのデバッグの開始](../debugger/get-started-debugging-multithreaded-apps.md)

スレッドデバッグ機能のツアー。 **[並列スタック]** ウィンドウと **[並列ウォッチ]** ウィンドウの機能を強調します。

 [スレッドとプロセスをデバッグするためのツール](../debugger/debug-threads-and-processes.md)

スレッドとプロセスをデバッグするためのツールの機能の一覧を示します。

 [複数プロセスをデバッグする](../debugger/debug-multiple-processes.md)

複数プロセスのデバッグ方法について説明します。

 [チュートリアル: [スレッド] ウィンドウを使用してデバッグする](../debugger/how-to-use-the-threads-window.md)。

**[スレッド]** ウィンドウと **[デバッグの場所]** ツールバーの使用方法を示すチュートリアルです。

 [チュートリアル: 並行アプリケーションをデバッグする](../debugger/walkthrough-debugging-a-parallel-application.md)

**[並列スタック]** ウィンドウと **[タスク]** ウィンドウの使用方法を示すチュートリアルです。

 [方法 : デバッグ中に別のスレッドに切り替える](../debugger/how-to-switch-to-another-thread-while-debugging.md)

デバッグコンテキストを別のスレッドに切り替えるには、いくつかの方法があります。

 [方法 : スレッドに対するフラグの設定と設定解除を行う](../debugger/how-to-flag-and-unflag-threads.md)

デバッグ中に特に注意する必要のあるスレッドにマークまたはフラグを設定する方法について説明します。

 [方法: 高パフォーマンス クラスター上でデバッグする](../debugger/how-to-debug-on-a-high-performance-cluster.md)

パフォーマンスの高いクラスター上で実行されるアプリケーションをデバッグする方法について説明します。

 [ネイティブ コード内のスレッドのデバッグのヒント](../debugger/tips-for-debugging-threads-in-native-code.md)

ネイティブ スレッドのデバッグに役立つ簡単な手法について説明します。

 [方法 : ネイティブ コードのスレッド名を設定する](../debugger/how-to-set-a-thread-name-in-native-code.md)

**[スレッド]** ウィンドウに表示するスレッド名の設定方法について説明します。

 [方法 : マネージド コードのスレッド名を設定する](../debugger/how-to-set-a-thread-name-in-managed-code.md)

**[スレッド]** ウィンドウに表示するスレッド名の設定方法について説明します。

## <a name="see-also"></a>関連項目

- [ブレークポイントの使用](../debugger/using-breakpoints.md)
- [スレッド化](/dotnet/standard/threading/index)
- [コンポーネントのマルチスレッド](https://msdn.microsoft.com/Library/2fc31e68-fb71-4544-b654-0ce720478779)
- [古いコードのマルチスレッドサポート](/cpp/parallel/multithreading-support-for-older-code-visual-cpp)
- [スレッドとプロセスをデバッグする](../debugger/debug-threads-and-processes.md)
- [リモート デバッグ](../debugger/remote-debugging.md)