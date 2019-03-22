---
title: IDebugApplication110 インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplication110 Interface
ms.assetid: ae943133-eb65-4ddc-a29f-9280a82dd8d6
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c040df103bac464e4f440f23674da966063f0ae
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58149670"
---
# <a name="idebugapplication110-interface"></a>IDebugApplication110 インターフェイス
`IDebugApplication110`インターフェイスの機能を拡張する、 [IDebugApplication インターフェイス](../../winscript/reference/idebugapplication-interface.md)します。 実装の QueryInterface を呼び出すことによってこのインターフェイスのインスタンスを取得できる[IDebugApplication インターフェイス](../../winscript/reference/idebugapplication-interface.md)します。  
  
> [!IMPORTANT]
>  このインターフェイスは、PDM v11.0 以降によって実装されます。 activdbg100.h にあります。  
  
## <a name="methods"></a>メソッド  
 `IDebugApplication110` インターフェイスは、以下のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugApplication110::SynchronousCallInMainThread](../../winscript/reference/idebugapplication110-synchronouscallinmainthread.md)|メイン スレッドで同期呼び出しを実行します。|  
|[IDebugApplication110::AsynchronousCallInMainThread](../../winscript/reference/idebugapplication110-asynchronouscallinmainthread.md)|メイン スレッドで非同期呼び出しを使用します。|  
|[IDebugApplication110::CallableWaitForHandles](../../winscript/reference/idebugapplication110-callablewaitforhandles.md)|シグナル状態になる一方で、指定したハンドルのいずれかの間、待機スレッド間の呼び出しをこのスレッドに投稿します。 このメソッドは、デバッガー スレッドから呼び出す必要があります。|