---
title: 'IDebugApplicationThread110:: IsSuspendedForBreakPoint |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThread110::IsSuspendedForBreakPoint
ms.assetid: 60688222-557f-4a43-a19b-846cee393cd0
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b0e70993b95ccffcf6041bb04f37af90667fc4fd
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574456"
---
# <a name="idebugapplicationthread110issuspendedforbreakpoint"></a>IDebugApplicationThread110::IsSuspendedForBreakPoint
このスレッドで[IDebugApplicationThreadEvents110:: OnSuspendForBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onsuspendforbreakpoint.md)が呼び出されていて、まだ完了していないかどうかを確認します。  
  
> [!IMPORTANT]
> [IDebugApplicationThread110 インターフェイス](../../winscript/reference/idebugapplicationthread110-interface.md)は、PDM version 11.0 以降で実装されています。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT IsSuspendedForBreakPoint([out, annotation("_Out_")] BOOL * pfIsSuspended);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pfIsSuspended`  
 [out] スレッドがブレークポイントで中断されている場合は `true`。それ以外の場合は `false`。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationThread110 インターフェイス](../../winscript/reference/idebugapplicationthread110-interface.md)