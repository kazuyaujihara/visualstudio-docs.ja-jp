---
title: JsDebugReadMemoryFlags 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- JsDebugReadMemoryFlags
apilocation:
- jscript9diag.dll
ms.assetid: 0d98d154-9cb1-49de-b2df-a2d029d343b7
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a1757678f20a01221ae46e1535d3190cd463d724
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571701"
---
# <a name="jsdebugreadmemoryflags-enumeration"></a>JsDebugReadMemoryFlags 列挙型
メモリの読み取り時の動作を指定するフラグ。  
  
## <a name="syntax"></a>構文  
  
```cpp
enum JsDebugReadMemoryFlags{   None = 0,   JsDebugAllowPartialRead= 0x1} JsDebugReadMemoryFlags;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="values"></a>値  
  
|名|説明|  
|----------|-----------------|  
|`JsDebugAllowPartialRead`|メモリの一部のみ正常に読み取られたときでも、呼び出し元で読み取り操作が正常に完了する必要がある場合に指定します。 このフラグを設定すると、"アドレス" が無効な場合のみ、E_JsDEBUG_INVALID_MEMORY_ADDRESS エラーが発生します。 このフラグを指定しない場合、要求したメモリのいずれかの部分を読み取れないと、E_JsDEBUG_INVALID_MEMORY_ADDRESS エラーが発生します。|  
|`None`|呼び出し元で ReadMemory の既定の動作が必要な場合に指定します。|  
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [Windows スクリプト インターフェイスのリファレンス](../../winscript/reference/windows-script-interfaces-reference.md)