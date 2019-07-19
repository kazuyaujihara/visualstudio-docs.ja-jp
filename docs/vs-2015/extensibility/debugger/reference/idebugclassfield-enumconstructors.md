---
title: IDebugClassField::EnumConstructors |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumConstructors
helpviewer_keywords:
- IDebugClassField::EnumConstructors method
ms.assetid: 66a250b2-75a0-45aa-8d58-40f91cc4bf7b
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cd93f4867221f0b42f91fe1f96b8a8b464bf5aa9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68191037"
---
# <a name="idebugclassfieldenumconstructors"></a>IDebugClassField::EnumConstructors
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このクラスのコンス トラクターの列挙子を作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT EnumConstructors(   
   CONSTRUCTOR_ENUM   cMatch,  
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumConstructors(  
   CONSTRUCTOR_ENUM     cMatch,   
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cMatch`  
 [in]値、 [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md)列挙体にコンス トラクターの型を指定する列挙体。  
  
 `ppEnum`  
 [out]返します、 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)コンス トラクターの一覧を表すオブジェクト。 コンス トラクターがない場合は、null 値を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK を返します。 またはコンス トラクターがない場合は S_FALSE を返します。 それ以外の場合はエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 列挙体の各要素は、 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)コンス トラクター メソッドを記述するオブジェクト。  
  
 通常、コンス トラクターの一覧では、コンパイラによって提供される既定のコンス トラクターは含まれません。  
  
## <a name="see-also"></a>関連項目  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md)
