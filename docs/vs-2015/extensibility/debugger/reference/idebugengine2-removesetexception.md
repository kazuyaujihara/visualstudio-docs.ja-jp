---
title: IDebugEngine2::RemoveSetException |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngine2::RemoveSetException
helpviewer_keywords:
- IDebugEngine2::RemoveSetException
ms.assetid: bdd25097-0e9d-4218-b417-0497ea48d2e8
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 53ba8c9c1934ee1c036e14fb51abd5babcf7e4c5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58974059"
---
# <a name="idebugengine2removesetexception"></a>IDebugEngine2::RemoveSetException
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

不要になったデバッグ エンジンによって処理されるように指定された例外を削除します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT RemoveSetException(   
   EXCEPTION_INFO* pException  
);  
```  
  
```csharp  
int RemoveSetException(   
   EXCEPTION_INFO[] pException  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pException`  
 [in][EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)を削除する例外を記述する構造体。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 例外を削除する必要があります設定されている以前に以前の呼び出しによって、 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)メソッド。  
  
 セットのすべての例外を一度に削除するには、呼び出し、 [RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md)メソッド。  
  
## <a name="see-also"></a>関連項目  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)
