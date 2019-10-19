---
title: 'IDebugApplicationThreadEvents110:: OnSuspendForBreakPoint |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThreadEvents110::OnSuspendForBreakPoint
ms.assetid: 224245ac-2aa2-43ae-97ed-493afc3d0122
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b5d73d7769dd48889a75da63da64be1d2977a088
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573339"
---
# <a name="idebugapplicationthreadevents110onsuspendforbreakpoint"></a>IDebugApplicationThreadEvents110::OnSuspendForBreakPoint
スレッドがブレークポイントに対して完全に中断され、通常の実行を再開していないかどうかを判断します。  
  
> [!IMPORTANT]
> [IDebugApplicationThreadEvents110 インターフェイス](../../winscript/reference/idebugapplicationthreadevents110-interface.md)は、PDM version 11.0 以降で実装されています。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT OnSuspendForBreakPoint( void );  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドにはパラメーターがありません。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationThreadEvents110 インターフェイス](../../winscript/reference/idebugapplicationthreadevents110-interface.md)