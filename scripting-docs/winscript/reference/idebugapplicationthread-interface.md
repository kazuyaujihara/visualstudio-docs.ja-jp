---
title: IDebugApplicationThread インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThread interface
ms.assetid: f869c328-4409-4b74-a6c3-9e63fc58c63d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a464085eddbea4f5d29c684c0f1dabc6f853b6d1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62822227"
---
# <a name="idebugapplicationthread-interface"></a>IDebugApplicationThread インターフェイス
言語エンジンとホスト スレッドの同期を行うと、スレッド固有のデバッグ状態情報を維持するために使用できます。 このインターフェイスは、拡張、`IRemoteDebugApplicationThread`スレッドへの非リモート アクセスを提供するインターフェイス。  
  
 継承されたメソッドだけでなく`IRemoteDebugApplicationThread`、`IDebugApplicationThread`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugApplicationThread::SynchronousCallIntoThread](../../winscript/reference/idebugapplicationthread-synchronouscallintothread.md)|呼び出し元アプリケーションのスレッドでコードを実行するためのメカニズムを提供します。|  
|[IDebugApplicationThread::QueryIsCurrentThread](../../winscript/reference/idebugapplicationthread-queryiscurrentthread.md)|このスレッドが現在実行中のスレッドを決定します。|  
|[IDebugApplicationThread::QueryIsDebuggerThread](../../winscript/reference/idebugapplicationthread-queryisdebuggerthread.md)|このスレッドがデバッガー スレッドであるかどうかを判断します。|  
|[IDebugApplicationThread::SetDescription](../../winscript/reference/idebugapplicationthread-setdescription.md)|このスレッドの説明を設定します。|  
|[IDebugApplicationThread::SetStateString](../../winscript/reference/idebugapplicationthread-setstatestring.md)|スレッドの状態の説明を設定します。|