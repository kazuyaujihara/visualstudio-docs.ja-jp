---
title: PENDING_BP_STATE_INFO | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- PENDING_BP_STATE_INFO
helpviewer_keywords:
- PENDING_BP_STATE_INFO structure
ms.assetid: 4d73ceff-43f9-4e95-8dba-88e1fab2def3
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: af22ef2d8a77b8c44b9e494736630480a0614162
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973166"
---
# <a name="pendingbpstateinfo"></a>PENDING_BP_STATE_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

コードの場所にバインドする準備が整っているブレークポイントの状態に関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
typedef struct _tagPENDING_BP_STATE_INFO {   
   PENDING_BP_STATE       state;  
   PENDING_BP_STATE_FLAGS flags;  
} PENDING_BP_STATE_INFO;  
```  
  
```csharp  
public struct PENDING_BP_STATE_INFO {   
   public uint state;  
   public uint flags;  
};  
```  
  
## <a name="members"></a>メンバー  
 state  
 値、 [PENDING_BP_STATE](../../../extensibility/debugger/reference/pending-bp-state.md)保留中のブレークポイントの状態を指定する列挙体。  
  
 フラグ  
 フラグの組み合わせ、 [PENDING_BP_STATE_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md)ブレークポイントが仮想化されたかどうかを指定する列挙体。  
  
## <a name="remarks"></a>Remarks  
 この構造体に渡される、 [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)メソッドでいっぱいになった場所。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)   
 [PENDING_BP_STATE](../../../extensibility/debugger/reference/pending-bp-state.md)   
 [PENDING_BP_STATE_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md)
