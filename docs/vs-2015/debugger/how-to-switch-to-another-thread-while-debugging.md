---
title: '方法: デバッグ中に別のスレッドに切り替える |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- threads, switching [debugging]
ms.assetid: 5cd76c52-76fa-4fcc-b37e-e9f0ecac0e9e
caps.latest.revision: 29
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8f481a0b1cb2142dc7dbfe11e17ac627753cebf0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68176515"
---
# <a name="how-to-switch-to-another-thread-while-debugging"></a>方法: デバッグ中に別のスレッドに切り替える
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

マルチスレッド アプリケーションをデバッグするとき、いくつかある方法のうちいずれかを使用して、現在作業中のスレッドから別のスレッドにコンテキストを切り替えることができます。  
  
### <a name="to-switch-to-any-thread-that-appears-in-the-threads-window"></a>[スレッド] ウィンドウで表示されるスレッドを切り替えるには  
  
- スレッドをダブルクリックします。  
  
### <a name="to-switch-to-a-thread-in-a-source-window"></a>ソース ウィンドウでスレッドを切り替えるには  
  
- 左側の余白でスレッド インジケーターを右クリックし、**に切り替える**、切り替え先のスレッドの名前をクリックします。 ショートカット メニューには、その場所にあるスレッドのみが表示されます。  
  
     インジケーターが表示されない場合で右クリックして、**スレッド**ウィンドウことを確認します**ソース スレッドを表示**が選択されています。  
  
### <a name="to-switch-to-a-thread-in-the-debug-location-toolbar"></a>[デバッグの場所] ツール バーでスレッドを切り替えるには  
  
1. **デバッグの場所**ツールバーで、をクリックして、**スレッド**ボックス。  
  
2. 一覧で、切り替え先のスレッドをクリックします。  
  
## <a name="see-also"></a>関連項目  
 [マルチスレッド アプリケーションのデバッグ](../debugger/debug-multithreaded-applications-in-visual-studio.md)
