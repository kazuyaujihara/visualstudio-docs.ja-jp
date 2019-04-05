---
title: スレッド |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c59ef3bdbbd96db82c8e865379907d95227628ab
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58976725"
---
# <a name="threads"></a>スレッド
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

デバッガーのアーキテクチャの観点から、**スレッド**:  
  
-   計算の基本的な単位です。 スレッドには、その手順を次に、1 つのコード コンテキストから移動を単一の呼び出し履歴のコンテキスト内で順番に実行します。  
  
-   それ自体で実行されているとおよびできるようという名前の中断、再開、プログラムを識別できます。 スレッドはまた、関連付けられているスタック フレームを列挙し、いくつかの条件下では、別のスタック フレームに移動できます。 スタック フレームのコンテキストを指定するには、スレッドを返せるその関連付けられた論理スレッド存在する場合。 スレッドには、IDE の [スレッド] ウィンドウで表示できる中断カウントなどのプロパティがあります。  
  
-   によって表される、 [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md)インターフェイス、通常、デバッグ エンジン (DE) またはプログラムを実行するための仮想マシンを作成します。  
  
## <a name="see-also"></a>関連項目  
 [プログラム](../../extensibility/debugger/programs.md)   
 [スタック フレーム](../../extensibility/debugger/stack-frames.md)   
 [デバッグ エンジン](../../extensibility/debugger/debug-engine.md)   
 [デバッガーの概念](../../extensibility/debugger/debugger-concepts.md)   
 [セッション デバッグ マネージャー](../../extensibility/debugger/session-debug-manager.md)
