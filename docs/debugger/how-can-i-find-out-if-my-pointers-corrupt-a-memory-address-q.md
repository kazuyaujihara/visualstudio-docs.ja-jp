---
title: ポインターを検索かどうか、破損しているメモリ アドレス |Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- addresses, pointers corrupting memory address
- memory, corruption
- pointers, corrupting memory addresses
- memory address corruption by pointers
- debugging [C++], memory corruption
- corrupted memory address
ms.assetid: a147c939-4fb1-415c-8410-cf303781e9e8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ebe87ef6c391f0beae7183c7baa396f5bd95cf02
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59366012"
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>ポインターがメモリ アドレスを破壊しているかどうか見つけるには
## <a name="problem-description"></a>問題の説明
 ポインターの 1 つがアドレス 0x00408000 のメモリを破壊してしまったようです。 どうなっているのか調べる方法はありますか。

## <a name="solution"></a>ソリューション

#### <a name="check-for-heap-corruption"></a>ヒープ破損のチェック

-   メモリの破損は、その多くがヒープの破損に起因します。 グローバル フラグ ユーティリティ (gflags.exe) または pageheap.exe を使用してください。 参照してください[ http://support.microsoft.com/default.aspx?scid=kb; en-ご; 286470](http://support.microsoft.com/default.aspx?scid=kb;en-us;286470)します。

#### <a name="to-find-where-the-memory-address-is-modified"></a>メモリ アドレスの変更箇所を見つけるには

1.  0x00408000 にデータ ブレークポイントを設定します。 「[データ変更ブレークポイントを設定する (ネイティブ C++ のみ)](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus)」を参照してください。

2.  ブレークポイントにヒットしたら、**[メモリ]** ウィンドウを使用して、0x00408000 から始まるメモリの内容を表示します。 詳細については、次を参照してください。[メモリ Windows](../debugger/memory-windows.md)します。

## <a name="see-also"></a>関連項目
- [ネイティブ コードのデバッグに関する FAQ](../debugger/debugging-native-code-faqs.md)
- [ネイティブ コードのデバッグ](../debugger/debugging-native-code.md)