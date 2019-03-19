---
title: IDebugApplication110::AsynchronousCallInMainThread |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplication110::AsynchronousCallInMainThread
ms.assetid: 13b80ff0-4bed-48c1-8031-d4147b51bf6c
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2fc497e6621b309eed8fbb7e7c4e79f1ebb24c9c
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58146618"
---
# <a name="idebugapplication110asynchronouscallinmainthread"></a>IDebugApplication110::AsynchronousCallInMainThread
メイン スレッドで非同期呼び出しを使用します。  
  
> [!IMPORTANT]
>  [IDebugApplication110 インターフェイス](../../winscript/reference/idebugapplication110-interface.md)PDM v11.0 以降によって実装された以降には。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT AsynchronousCallInMainThread([in] IDebugThreadCall* pptc, [in] DWORD_PTR dwParam1, [in] DWORD_PTR dwParam2, [in] DWORD_PTR dwParam3);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pptc`  
 [IDebugThreadCall インターフェイス](../../winscript/reference/idebugthreadcall-interface.md)を呼び出すオブジェクト。  
  
 `dwParam1`  
 呼び出しの最初のパラメーター。  
  
 `dwParam1`  
 呼び出しの最初のパラメーター。  
  
 `dwParam2`  
 呼び出しの 2 番目のパラメーター。  
  
 `dwParam3`  
 呼び出しの 3 番目のパラメーター。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplication110 インターフェイス](../../winscript/reference/idebugapplication110-interface.md)