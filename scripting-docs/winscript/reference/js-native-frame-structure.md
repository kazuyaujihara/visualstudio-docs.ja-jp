---
title: JS_NATIVE_FRAME 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- JS_NATIVE_FRAME
apilocation:
- jscript9diag.dll
ms.assetid: 5afa2ee1-b3e2-47cb-b304-84f96e6fbb14
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a0777cf42b9ed9412602cb34ed2d521deca1fb9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62968673"
---
# <a name="jsnativeframe-structure"></a>JS_NATIVE_FRAME 構造体
スタック フレームを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef struct {  
    UINT64 InstructionOffset;    UINT64 ReturnOffset;    UINT64 FrameOffset;    UINT64 StackOffset;  
} JS_NATIVE_FRAME;  
```  
  
## <a name="members"></a>メンバー  
 `InstructionOffset`  
 命令ポインター。  
  
 `ReturnOffset`  
 リターン アドレス。  
  
 `FrameOffset`  
 フレーム ポインター。  
  
 `StackOffset`  
 スタック ポインター。  
  
## <a name="remarks"></a>Remarks  
 `JS_NATIVE_FRAME` 構造体は `IJsStackFrameEnumerator` で使用されます。  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト デバッガーの定数、列挙型、および構造体](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)