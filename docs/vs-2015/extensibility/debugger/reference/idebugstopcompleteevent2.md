---
title: IDebugStopCompleteEvent2 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugStopCompleteEvent2 interface
ms.assetid: ff3e89f4-61bb-489d-901c-447260100218
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a9c2a6a6e69bf47751706710801dd78c832ccd2c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58962578"
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

デバッグ エンジン (DE) は、プログラムが停止した場合は、この省略可能なイベントをセッション デバッグ マネージャー (SDM) に送信できます。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugStopCompleteEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 これは、新しいインターフェイス[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]します。 以前のリリースでは、非同期の停止はサポートされていませんでした。  
  
 [停止](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)はマルチ プロセスまたは複数のプログラムのシナリオで SDM によって呼び出されます。 1 つのプログラムは、SDM を停止してからイベントを送信するとき、SDM を停止するには、他のプログラムを要求します。  
  
 SDM プログラムが停止したことを非同期に通知するために使用されます。 場合によってコードが実行されているないデバッグ対象のプログラム内で、これは、インタープリターのデバッグ エンジンに役立ちますように[停止](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)同期的に完了できません。 デバッグ エンジンがこの非同期通知を使用するか、返す必要があります`S_ASYNC_STOP`から[停止](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)します。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll
