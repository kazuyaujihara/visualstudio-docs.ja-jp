---
title: BP_PASSCOUNT |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- BP_PASSCOUNT
helpviewer_keywords:
- BP_PASSCOUNT structure
ms.assetid: 791ac175-b897-4c70-873e-240da7e0ac89
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b99cbd777755a9a48869299b5cea523ecacbb4a4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68153375"
---
# <a name="bppasscount"></a>BP_PASSCOUNT
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

条件付きブレークポイントが発生する、カウントと条件について説明します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
typedef struct _BP_PASSCOUNT {   
   DWORD              dwPassCount;  
   BP_PASSCOUNT_STYLE stylePassCount;  
} BP_PASSCOUNT;  
```  
  
```csharp  
public struct BP_PASSCOUNT {   
   public uint dwPassCount;  
   public uint stylePassCount;  
};  
```  
  
## <a name="members"></a>メンバー  
 `dwPassCount`  
 それを起動する前に、ブレークポイントを渡すための時間数。  
  
 `stylePassCount`  
 値、 [BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md)ブレークポイントのスタイルを指定する列挙体は、数を渡します。  
  
## <a name="remarks"></a>Remarks  
 この構造体のメンバーである、 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)構造体。  
  
 この構造体がパラメーターとして渡されるも、[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)と[SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)メソッド。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)   
 [BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md)
