---
title: IDebugApplicationThreadEvents110::OnSuspendForBreakPoint |Microsoft Docs
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
ms.openlocfilehash: 1e6a663d6c1e504d8e10ea26d7d5b395b5ba8025
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58153085"
---
# <a name="idebugapplicationthreadevents110onsuspendforbreakpoint"></a>IDebugApplicationThreadEvents110::OnSuspendForBreakPoint
スレッドはブレークポイントを設定する完全に中断し、通常の実行を再開ができないかどうかを判断します。  
  
> [!IMPORTANT]
>  [IDebugApplicationThreadEvents110 インターフェイス](../../winscript/reference/idebugapplicationthreadevents110-interface.md)PDM v11.0 以降によって実装された以降には。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT OnSuspendForBreakPoint( void );  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドにパラメーターがありません。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationThreadEvents110 インターフェイス](../../winscript/reference/idebugapplicationthreadevents110-interface.md)