---
title: IDebugObject::IsNullReference |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugObject::IsNullReference
helpviewer_keywords:
- IDebugObject::IsNullReference method
ms.assetid: 6dbfcdb0-954f-4486-8fac-7ea8d003e3a9
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cd116b236eb57e2fab638cfaa8412167a6d1180f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977159"
---
# <a name="idebugobjectisnullreference"></a>IDebugObject::IsNullReference
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このオブジェクトが null 参照であるかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT IsNullReference(   
   BOOL* pfIsNull  
);  
```  
  
```csharp  
int IsNullReference(  
   out int pfIsNull  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pfIsNull`  
 [out]0 以外を返します (`TRUE`) 0 を返しますそれ以外の場合、このオブジェクトが null 参照。 場合 (`FALSE`)。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 Null 参照は、空のオブジェクトまたはオブジェクトに割り当てられていないを意味します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
