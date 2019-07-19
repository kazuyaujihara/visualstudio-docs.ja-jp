---
title: IDebugObject::IsProxy |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugObject::IsProxy
- IsProxy
ms.assetid: 06c66b87-db95-4400-ab26-5d33e743a439
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0777a7e9696009124841ba177af70e5a23a6ea52
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68180514"
---
# <a name="idebugobjectisproxy"></a>IDebugObject::IsProxy
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

オブジェクトが透過プロキシであるかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT IsProxy (  
   BOOL* pfIsProxy  
);  
```  
  
```csharp  
int IsProxy (  
   out bool pfIsProxy  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pfIsProxy`  
 [out]`TRUE`オブジェクトが透過プロキシの場合、それ以外の場合、`FALSE`します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、既定の C++ デバッグ エンジンによって実装されます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
