---
title: IDebugEnumField::GetStringFromValue |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEnumField::GetStringFromValue
helpviewer_keywords:
- IDebugEnumField::GetStringFromValue method
ms.assetid: 5f95fd0c-fdce-497f-9f54-2ad8749494e9
caps.latest.revision: 6
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 98d7e976e0cd37ad1397666471c89da3d47d45d3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62920319"
---
# <a name="idebugenumfieldgetstringfromvalue"></a>IDebugEnumField::GetStringFromValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このメソッドは、その値を指定された列挙定数の名前を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetStringFromValue(  
   ULONGLONG value,  
   BSTR*     pbstrValue  
);  
```  
  
```csharp  
int GetStringFromValue(  
   ulong      value,  
   out string pbstrValue  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `value`  
 [in]定数、列挙型の名前を取得する対象の値。  
  
 `pbstrValue`  
 [out]列挙定数の名前を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`場合は、値は、関連付けの名前がないか、エラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 同じ値に関連付けられている 1 つ以上の名前がある場合は、列挙で定義されている最初の名前が返されます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)
