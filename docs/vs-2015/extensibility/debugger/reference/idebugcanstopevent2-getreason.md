---
title: IDebugCanStopEvent2::GetReason |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugCanStopEvent2::GetReason
helpviewer_keywords:
- IDebugCanStopEvent2::GetReason
ms.assetid: f5de31ca-7b8d-4029-9cf9-ba860ac66af6
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 707488abed004adaa75c84f16358bdd8a979eb71
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58972977"
---
# <a name="idebugcanstopevent2getreason"></a>IDebugCanStopEvent2::GetReason
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

なぜデバッグ エンジン (DE) を停止する必要がある理由を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetReason(   
   CANSTOP_REASON* pcr  
);  
```  
  
```csharp  
int GetReason(   
   out enum_CANSTOP_REASON pcr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pcr`  
 [out]値を返します、 [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)このイベントの理由を説明する列挙体。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドの呼び出しの前に通常、 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)メソッドの呼び出し元は、0 以外を渡すかどうかを判断できるように (`TRUE`) に、`IDebugCanStopEvent2::CanStop`メソッド。  
  
 停止の理由には、いずれかを指定できる`CANSTOP_ENTRYPOINT`、エントリ ポイントに達した、DE つまりまたは`CANSTOP_STEPIN`関数にステップ インは、DE つまりします。  
  
## <a name="see-also"></a>関連項目  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)   
 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)
