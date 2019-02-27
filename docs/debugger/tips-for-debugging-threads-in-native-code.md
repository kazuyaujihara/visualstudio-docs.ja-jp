---
title: ネイティブ コード内のスレッドをデバッグするためのヒント |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], threads
ms.assetid: 0374c8c6-57a3-4cfe-8047-2effef5ff5dc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 8f76a6ea66396a8c5780731945cad87eab94b8ee
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56717599"
---
# <a name="tips-for-debugging-threads-in-native-code"></a>ネイティブ コード内のスレッドのデバッグのヒント
ここでは、ネイティブ コード内のスレッドをデバッグするときに役立つヒントを紹介します。

-   **[ウォッチ]** ウィンドウまたは **[クイック ウォッチ]** ダイアログ ボックスで「`@TIB`」と入力すると、[スレッド情報ブロック] の内容を表示できます。

-   **[ウォッチ]** ウィンドウまたは **[クイック ウォッチ]** ダイアログ ボックスで「`@Err`」と入力すると、現在のスレッドの最終エラー コードを表示できます。

-   マルチスレッド アプリケーションのデバッグには、C ランタイム ライブラリ (CRT) 関数を使用できます。 詳細については、「[_malloc_dbg](/cpp/c-runtime-library/reference/malloc-dbg)」をご覧ください。

## <a name="see-also"></a>参照
- [マルチスレッド アプリケーションのデバッグ](../debugger/debug-multithreaded-applications-in-visual-studio.md)
- [ネイティブ コードのデバッグ](../debugger/debugging-native-code.md)