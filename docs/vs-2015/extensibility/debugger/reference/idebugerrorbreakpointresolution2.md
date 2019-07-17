---
title: IDebugErrorBreakpointResolution2 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugErrorBreakpointResolution2
helpviewer_keywords:
- IDebugErrorBreakpointResolution2
ms.assetid: b1234216-0ac8-461d-b2a7-54f60f8f3262
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e39a64cf0c7e5f41102f55c774526510bd3ea32d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68183529"
---
# <a name="idebugerrorbreakpointresolution2"></a>IDebugErrorBreakpointResolution2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このインターフェイスは、ブレークポイントのエラーの解像度を表します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugErrorBreakpointResolution2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 デバッグ エンジンでは、ブレークポイントのサポートの一部として、このインターフェイスを実装します。 このインターフェイスは、ブレークポイントがバインドに失敗しましたをレポートに使用されます。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 呼び出し[GetBreakpointResolution](../../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md)ブレークポイントがバインドに失敗した場所の情報を提供するには、このインターフェイスを返します。 [GetErrorBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md)メソッドは、取得、 [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)インターフェイス。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 次の表は、メソッドの`IDebugErrorBreakpointResolution2`します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetBreakpointType](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getbreakpointtype.md)|ブレークポイントの種類を取得します。|  
|[GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)|ブレークポイント解像度の情報を取得します。|  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)   
 [GetBreakpointResolution](../../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md)   
 [GetErrorBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md)
