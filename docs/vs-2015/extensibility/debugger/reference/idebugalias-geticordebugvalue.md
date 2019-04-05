---
title: IDebugAlias::GetICorDebugValue |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugAlias::GetICorDebugValue
helpviewer_keywords:
- IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 67ab8a7343cd320470515b757dfca905a0a4690e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58976098"
---
# <a name="idebugaliasgeticordebugvalue"></a>IDebugAlias::GetICorDebugValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このエイリアスに関連付けられている値を表すマネージ コード インターフェイスを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetICorDebugValue(  
   IUnknown** ppUnk  
);  
```  
  
```csharp  
int GetICorDebugValue(  
   out object ppUnk  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppUnk`  
 [out]`IUnknown`このエイリアスに関連付けられている値を表すインターフェイスです。 このインターフェイスを照会できます、`ICorDebugValue`インターフェイス。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、管理対象の値のみに適用されます (、`ICorDebugValue`インターフェイスでは、[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]で定義されていると、 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK では cordebug.idl ファイル)。  
  
## <a name="see-also"></a>関連項目  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)
