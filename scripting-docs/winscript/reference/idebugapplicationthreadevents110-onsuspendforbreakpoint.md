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
ms.openlocfilehash: a9e39af9784b139e935c271fca6db565136352cf
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440422"
---
# <a name="idebugapplicationthreadevents110onsuspendforbreakpoint"></a>IDebugApplicationThreadEvents110::OnSuspendForBreakPoint
スレッドはブレークポイントを設定する完全に中断し、通常の実行を再開ができないかどうかを判断します。  
  
> [!IMPORTANT]
> [IDebugApplicationThreadEvents110 インターフェイス](../../winscript/reference/idebugapplicationthreadevents110-interface.md)PDM v11.0 以降によって実装された以降には。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT OnSuspendForBreakPoint( void );  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドにパラメーターがありません。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationThreadEvents110 インターフェイス](../../winscript/reference/idebugapplicationthreadevents110-interface.md)