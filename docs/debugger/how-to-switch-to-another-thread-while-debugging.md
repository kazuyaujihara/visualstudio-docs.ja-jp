---
title: デバッグ中に別のスレッドに切り替える
ms.custom: seodec18
ms.date: 04/27/2017
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threads, switching [debugging]
ms.assetid: 5cd76c52-76fa-4fcc-b37e-e9f0ecac0e9e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 11ad6280ad1213008bbb8ca8f6311ca34231d308
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72732444"
---
# <a name="how-to-switch-to-another-thread-while-debugging-in-visual-studio-c-visual-basic-c"></a>方法: Visual Studio でのデバッグ中に別のスレッドにC#切り替える (、 C++Visual Basic、)
マルチスレッドアプリケーションをデバッグする場合、いくつかのメソッドのいずれかを使用して、使用していたスレッドから別のスレッドに切り替えることができます。

> [!NOTE]
> スレッドの実行順序を制御する場合は、[スレッドの凍結と凍結](../debugger/get-started-debugging-multithreaded-apps.md)解除を行う必要があります。

コードエディターおよびさまざまなマルチスレッドデバッグウィンドウでスレッドを調べると、黄色の矢印は現在のスレッドを示します。 尾が付いた緑色の矢印は、現在のスレッドが現在のデバッガーコンテキストを持っていることを示します。

### <a name="to-switch-to-any-thread-that-appears"></a>表示される任意のスレッドに切り替えるには

- **[スレッド]** ウィンドウまたは **[並列ウォッチ]** ウィンドウで、スレッドをダブルクリックします。

### <a name="to-switch-to-a-thread-in-a-source-window"></a>ソース ウィンドウでスレッドを切り替えるには

- 左側の余白で、スレッドマーカーアイコン![スレッドマーカー](../debugger/media/dbg-thread-marker.png "ThreadMarker")を右クリックし、 **[切り替え先]** をポイントして、切り替え先のスレッドの名前をクリックします。 ショートカット メニューには、その場所にあるスレッドのみが表示されます。

     スレッドマーカーが表示されない場合は、 **[スレッド]** ウィンドウ内を右クリックし、 **[ソースにスレッドを表示]** する が選択されていることを確認します。

### <a name="to-switch-to-a-thread-in-the-debug-location-toolbar"></a>[デバッグの場所] ツール バーでスレッドを切り替えるには

1. **[デバッグの場所]** ツールバーで、 **[スレッド]** ボックスの一覧をクリックします。

2. 一覧で、切り替え先のスレッドをクリックします。

## <a name="see-also"></a>関連項目
- [マルチスレッド アプリケーションのデバッグ](../debugger/debug-multithreaded-applications-in-visual-studio.md)
