---
title: IDebugBreakpointBoundEvent2::EnumBoundBreakpoints |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugBreakpointBoundEvent2::EnumBoundBreakpoints
helpviewer_keywords:
- IDebugBreakpointBoundEvent2::EnumBoundBreakpoints
ms.assetid: 1f588feb-522e-488d-be92-7bc19b9e3688
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: bc3d38344dccf93f4b032357b2cdef88a0a4a242
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973841"
---
# <a name="idebugbreakpointboundevent2enumboundbreakpoints"></a>IDebugBreakpointBoundEvent2::EnumBoundBreakpoints
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このイベントにバインドされているブレークポイントの列挙子を作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT EnumBoundBreakpoints(   
   IEnumDebugBoundBreakpoints2** ppEnum  
);  
```  
  
```csharp  
int EnumBoundBreakpoints(   
   out IEnumDebugBoundBreakpoints2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppEnum`  
 [out]返します、 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)このイベントからのすべてのブレークポイントを列挙するオブジェクトがバインドされています。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`バインドされたブレークポイントがない場合、それ以外の場合、エラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 バインドされたブレークポイントの一覧は、このイベントをそれらのバインドはあり、バインド保留中のブレークポイントからブレークポイントのリスト全体ができない可能性があります。 保留中のブレークポイントにバインドされているすべてのブレークポイントの一覧を取得する、 [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md)取得、関連付けられている[IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)オブジェクトを呼び出して、 [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)を取得するメソッド、 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)保留中のブレークポイントのバインドされたすべてのブレークポイントを含むオブジェクト。  
  
## <a name="example"></a>例  
 次の例では、このメソッドを実装する方法を示しています、 **CBreakpointSetDebugEventBase**を公開するオブジェクト、 [IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)インターフェイス。  
  
```cpp#  
STDMETHODIMP CBreakpointSetDebugEventBase::EnumBoundBreakpoints(  
    IEnumDebugBoundBreakpoints2 **ppEnum)  
{  
    HRESULT hRes = E_FAIL;  
  
    if ( ppEnum )  
    {  
        if ( m_pEnumBound )  
        {  
            hRes = m_pEnumBound->Clone(ppEnum);  
  
            if ( EVAL(S_OK == hRes) )  
                (*ppEnum)->Reset();  
        }  
        else  
            hRes = E_FAIL;  
    }  
    else  
        hRes = E_INVALIDARG;  
  
    return ( hRes );  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)   
 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)   
 [GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)
