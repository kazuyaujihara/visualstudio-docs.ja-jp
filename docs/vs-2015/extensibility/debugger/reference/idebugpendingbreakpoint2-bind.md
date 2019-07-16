---
title: IDebugPendingBreakpoint2::Bind |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPendingBreakpoint2::Bind
helpviewer_keywords:
- Bind method
- IDebugPendingBreakpoint2::Bind method
ms.assetid: 46e3f307-219d-40cd-a929-d41399c60ecf
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 33cdcad38e2f46962120dcd63c1be21675060be0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194536"
---
# <a name="idebugpendingbreakpoint2bind"></a>IDebugPendingBreakpoint2::Bind
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

この保留中のブレークポイントをコードの 1 つまたは複数の場所にバインドします。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT Bind(   
   void   
);  
```  
  
```csharp  
int Bind();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。 返します`E_BP_DELETED`ブレークポイントが削除されている場合。  
  
## <a name="remarks"></a>Remarks  
 このメソッドが呼び出されると、デバッグ エンジン (DE) する必要がありますに一致するすべてのコードの場所にこの保留中のブレークポイントをバインドしようとします。  
  
 このメソッドから制御が戻る後、呼び出し元が保留中のブレークポイントがバインドされていることを示すエラーとして扱う前に、イベントへの呼び出しを待機する必要があります、 [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)または[EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)メソッドとは、バインドまたはエラーですべてのブレークポイントをそれぞれ列挙されます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)   
 [IDebugBreakpointErrorEvent2](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)   
 [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)   
 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)
