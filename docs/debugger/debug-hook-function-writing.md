---
title: デバッグ用フック関数の作成 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vc.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], CRT debug support
- debug hook functions
- hooks, debug
- hooks
- debugging [CRT], debug hook functions
ms.assetid: 5510635f-cf69-4907-b72d-ae27af1f19af
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 82145d39adc519bfd1324cc36805cea7b97b1664
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62563374"
---
# <a name="debug-hook-function-writing"></a>デバッグ用フック関数の作成
ここでは、カスタムで作成できるさまざまなデバッグ用フック関数について説明します。デバッグ用フック関数を使用すると、デバッガーが通常行う処理内部の定義済みの位置にコードを挿入できます。

## <a name="in-this-section"></a>このセクションの内容
 [Client ブロック用のフック関数](../debugger/client-block-hook-functions.md)を検証または _client_block に格納されているデータの内容をレポートする関数を記述するためのガイダンスとプロトタイプを提供します。

 [割り当てフック関数](../debugger/allocation-hook-functions.md)割り当てフック関数を定義、その別の使用法を紹介、制限事項、指摘およびプロトタイプを提供します。

 [割り当てフック関数と CRT メモリ割り当て](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)割り当てフック関数を明示的に無視するので、制限について説明します`_CRT_BLOCK`ブロック内部のメモリを割り当てる C ランタイム ライブラリ関数を呼び出す場合。 また、割り当てフック関数が `_CRT_BLOCK` ブロックを無視しない場合の結果を例と共に示し、既定の割り当てフック関数 **CrtDefaultAllocHook** を変更する方法について説明します。

 [レポート用のフック関数](../debugger/report-hook-functions.md)について説明します`_CrtSetReportHook`割り当ての特定の種類に注目するレポートをフィルター処理に使用することができます。 また、プロトタイプを説明します。

## <a name="related-sections"></a>関連項目

- [CRT のデバッグ技術](../debugger/crt-debugging-techniques.md)-CRT デバッグのライブラリが、レポート用マクロの使用など、C ランタイム ライブラリのデバッグ手法へのリンクが相違`malloc`と`_malloc_dbg`デバッグ用フック関数とは CRT の書き込みデバッグ ヒープ。