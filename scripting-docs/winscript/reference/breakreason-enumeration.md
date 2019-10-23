---
title: BREAKREASON 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- BREAKREASON
apilocation:
- scrobj.dll
helpviewer_keywords:
- BREAKREASON enumeration
ms.assetid: bde07ede-2f9b-4fa2-affc-f9405683f5f7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6f656bdf4e3bc85a014ff8d3011708799aa44bcd
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572625"
---
# <a name="breakreason-enumeration"></a>BREAKREASON 列挙型
中断の原因を示します。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef enum tagBREAKREASON {  
   BREAKREASON_STEP,  
   BREAKREASON_BREAKPOINT,  
   BREAKREASON_DEBUGGER_BLOCK,  
   BREAKREASON_HOST_INITIATED,  
   BREAKREASON_LANGUAGE_INITIATED,  
   BREAKREASON_DEBUGGER_HALT,  
   BREAKREASON_ERROR,  
   BREAKREASON_JIT  
} BREAKREASON;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|BREAKREASON_STEP|言語エンジンは、ステップ実行モードです。|  
|BREAKREASON_BREAKPOINT|言語エンジンで、明示的なブレークポイントが検出されました。|  
|BREAKREASON_DEBUGGER_BLOCK|言語エンジンで、別のスレッドでデバッガーブロックが検出されました。|  
|BREAKREASON_HOST_INITIATED|ホストが中断を要求しました。|  
|BREAKREASON_LANGUAGE_INITIATED|言語エンジンは中断を要求しました。|  
|BREAKREASON_DEBUGGER_HALT|デバッガー IDE が中断を要求しました。|  
|BREAKREASON_ERROR|中断の原因となった実行エラーが発生しました。|  
|BREAKREASON_JIT|JIT デバッグの開始によって発生しました。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト デバッガーの定数、列挙型、および構造体](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)