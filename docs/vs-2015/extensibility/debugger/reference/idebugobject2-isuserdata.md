---
title: IDebugObject2::IsUserData |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugObject2::IsUserData
helpviewer_keywords:
- IDebugObject2::IsUserData method
ms.assetid: 6ffa0d0e-f742-496d-acc7-db74c248bc45
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: fd595ce041ae1968e085e3b63b49d308cfd14452
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194578"
---
# <a name="idebugobject2isuserdata"></a>IDebugObject2::IsUserData
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

オブジェクトがユーザー データを表すかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT IsUserData(  
   BOOL* pfUser  
);  
```  
  
```csharp  
int IsUserData(  
   out int pfUser  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pfUser`  
 [out]0 以外の値を返します (`TRUE`) オブジェクトは、ユーザー データを表している場合は 0 (`FALSE`) そうでない場合。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 ユーザー データとは、JustMyCode (そのため、スタック トレースに表示し、ユーザー コードとしてモジュールをマークするユーザー構成可能なオプション) として指定されたモジュールの一部であるオブジェクトです。  
  
## <a name="see-also"></a>関連項目  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)
