---
title: 何をデバッグするとしますか。
description: アプリをデバッグする意味を理解します。
ms.custom: debug-experiments
ms.date: 10/17/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugger
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bece83e7e2a66499721c017932d4b498b664b459
ms.sourcegitcommit: a34b7d4fdb3872865fcf98ba24a0fced58532adc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2018
ms.locfileid: "51561828"
---
# <a name="what-is-debugging"></a>何をデバッグするとしますか。

Visual Studio デバッガーは、強力なツールです。 など、いくつかの用語について説明する前に、それを使用する方法を説明します*デバッガー*、*デバッグ*、および*デバッグ モード*します。 これにより、検索と、バグ修正について後で説明するは後ほどほぼ同じです。

## <a name="debugger-vs-debugging"></a>デバッガーとデバッグ

用語*デバッグ*は非常に一般的なと、多くのさまざまなことを意味することができます。 単語の最もリテラルの使用法 で、コードからのバグの削除を意味します。 ここで、これを行う方法の多くがあります。 たとえば、入力ミスを探して、コードをスキャンして、またはコード アナライザーを使用して、デバッグする場合があります。 パフォーマンス プロファイラーを使用してコードをデバッグする場合があります。 またはを使用してデバッグする場合があります、*デバッガー*します。

デバッガーは、非常に特殊な開発者ツールです。 デバッガーは、実行中のアプリにアタッチされ、コードを検査することができます。 Visual Studio のデバッグ ドキュメントでは、これは通常「デバッグ」ということを意味します。

## <a name="debug-mode-vs-running-your-app"></a>モードのアプリの実行とデバッグします。

Visual Studio で初めてのアプリを実行するときに、緑色の矢印ボタンを押して開始可能性があります![デバッグの開始](../debugger/media/dbg-tour-start-debugging.png "デバッグの開始")ツールバー。 既定で、**デバッグ**値、左のドロップダウン リストに表示されます。 Visual Studio に慣れていない場合、アプリのデバッグが実行中に何かという印象のままにこのことができますをアプリがどの it は--が、これら 2 つの非常にさまざまなタスクは、根本的にします。

![デバッグ ビルドを選択します。](../debugger/media/what-is-debugging-debug-build.png)

A**デバッグ**値がデバッグ構成ことを示します。 アプリを起動すると (緑色の矢印キーを押してまたは**f5 キーを押して**) でアプリを起動するデバッグ構成を*デバッグ モード*、つまりデバッガーをアタッチでアプリを実行して、します。 これにより、デバッグ、アプリでのバグの発見に使用できる機能の完全なセットです。

プロジェクトを開いてがある場合は、ドロップダウン セレクターが書かれている場所を選択**デバッグ**選択**リリース**代わりにします。

![リリース ビルドを選択します。](../debugger/media/what-is-debugging-release-build.png)

この設定を切り替えると、デバッグ構成から、リリース構成に、プロジェクトを変更します。 Visual Studio プロジェクトでは、ご使用のプログラムに対応するリリースとデバッグ構成を個別に用意しています。 デバッグでのデバッグ バージョンを最終リリース配布用のリリース バージョンをビルドします。 リリース ビルドがパフォーマンスを最適化されていますが、デバッグ、デバッグ ビルドをお勧めします。

## <a name="when-to-use-a-debugger"></a>デバッガーを使用する場合

デバッガーは、不可欠なツールを見つけて、アプリでバグを修正します。 ただし、コンテキストは、キング、およびに迅速にバグまたはエラーを排除するため、破棄可能なすべてのツールを活用することが重要です。 場合によっては、「ツール」の右側には、もっと優れたコーディングのプラクティスがあります。 他のツールと、デバッガーを使用する場合を学習しても、デバッガーをより効果的に使用する方法を学習します。 既にデバッガーについて学習する必要があるをわかっている場合は、次を参照してください。[超初心者向けのデバッグ](../debugger/debugging-absolute-beginners.md)します。 それ以外の場合、次のリンク**次のステップ**します。

## <a name="next-steps"></a>次の手順

この記事では、いくつかの一般的なデバッグの概念を学びました。 次に、Visual Studio でデバッグする方法とバグでコードを作成する方法について学習を開始できます。

> [!div class="nextstepaction"]
> [優れたC#Visual Studio を使用するコード](../debugger/write-better-code-with-visual-studio.md)
