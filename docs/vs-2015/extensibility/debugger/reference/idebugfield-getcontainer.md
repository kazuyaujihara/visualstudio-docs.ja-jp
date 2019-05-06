---
title: IDebugField::GetContainer |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugField::GetContainer
helpviewer_keywords:
- IDebugField::GetContainer method
ms.assetid: 6d6c8213-6181-4adf-9584-3e4cac163dd8
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6f6c5b0cb1b14ac7cc34e284e2d073fafed9b20e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62547131"
---
# <a name="idebugfieldgetcontainer"></a>IDebugField::GetContainer
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このメソッドは、フィールドのコンテナーを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetContainer(   
   IDebugContainerField** ppContainerField  
);  
```  
  
```csharp  
int GetContainer(  
   out IDebugContainerField ppContainerField  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppContainerField`  
 [out]によって表されるコンテナーを返します、 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)インターフェイス。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このフィールドが、返された、コンテナーを持たないかどうか`ppContainerField`は null 値になります。  
  
## <a name="see-also"></a>関連項目  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)
