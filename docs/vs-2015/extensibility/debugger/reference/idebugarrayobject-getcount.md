---
title: 'IDebugArrayObject:: GetCount |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetCount
helpviewer_keywords:
- IDebugArrayObject::GetCount method
ms.assetid: 7931f3f7-033c-4bf8-8abd-95183952ebb0
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 35cce37afc389501386ffec7b75b934e7933bc98
ms.sourcegitcommit: 9cfd3ef6c65f671a26322320818212a1ed5955fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68197801"
---
# <a name="idebugarrayobjectgetcount"></a>IDebugArrayObject::GetCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

配列内の要素の数を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
[C++]  
HRESULT GetCount(   
   DWORD* pdwElements  
);  
```  
  
```  
[C#]  
int GetCount(  
   out uint pdwElements  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pdwElements`  
 入出力カウントを返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、は S_OK を返します。それ以外の場合は、エラーコードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、配列オブジェクトが多次元であっても、配列オブジェクトのすべての要素を1次元配列として表示します。 たとえば、配列`myarray[3][2][6]`の場合、このメソッドは`pdwElements`パラメーターで36を返します。 [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)メソッドを使用して、一度に1つずつ個別の要素を取得します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)
