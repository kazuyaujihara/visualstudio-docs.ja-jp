---
title: IDebugBreakpointResolution2 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugBreakpointResolution2
helpviewer_keywords:
- IDebugBreakpointRequest2 interface
ms.assetid: 451d5bce-b9c1-48ff-beaa-2b4c3e1ceea0
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 031d8ffab94239c6169a61f3748172787267043c
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "58963794"
---
# <a name="idebugbreakpointresolution2"></a>IDebugBreakpointResolution2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このインターフェイスは、バインドされたブレークポイントを説明する情報を表します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugBreakpointResolution2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 デバッグ エンジン (DE) は、ブレークポイントのサポートの一部として、このインターフェイスを実装します。 このインターフェイスは、ブレークポイントのプロパティを表示すると、セッション デバッグ マネージャーが使用するバインドされたブレークポイントの説明を提供します。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 呼び出し[GetBreakpointResolution](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md)このインターフェイスを返します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 次の表は、メソッドの`IDebugBreakpointResolution2`します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetBreakpointType](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getbreakpointtype.md)|この解像度によって表されるブレークポイントの種類を取得します。|  
|[GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)|このブレークポイントを表すブレークポイント解像度の情報を取得します。|  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [GetBreakpointResolution](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md)
