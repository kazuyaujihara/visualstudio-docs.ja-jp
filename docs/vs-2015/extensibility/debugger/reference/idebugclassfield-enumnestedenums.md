---
title: IDebugClassField::EnumNestedEnums |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumNestedEnums
helpviewer_keywords:
- IDebugClassField::EnumNestedEnums method
ms.assetid: 90fd0cef-9145-4de6-91d4-6c881df39d6e
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 84f60b9b0c882883c930657df59530f1c5107a22
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "59000990"
---
# <a name="idebugclassfieldenumnestedenums"></a>IDebugClassField::EnumNestedEnums
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このクラスの入れ子になった列挙子の列挙子を作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT EnumNestedEnums(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumNestedEnums(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppEnum`  
 [out]返します、 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)入れ子になった列挙体のリストを表すオブジェクト。 入れ子になった列挙型がない場合は、null 値を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK を返します。 または入れ子になった列挙子がない場合は S_FALSE を返します。 それ以外の場合はエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 列挙体の各要素は、 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)入れ子になった列挙型を記述するオブジェクト。  
  
 クラス内で宣言された列挙体は、入れ子になった列挙型と見なされます。 次に例を示します。  
  
```  
class RootClass {  
   enum NestedEnum { EnumValue = 0 }  
};  
```  
  
 `EnumNestedEnums`メソッドは、 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)オブジェクトを 1 つ含む[IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)を表すオブジェクトを`NestedEnum`列挙体。  
  
## <a name="see-also"></a>関連項目  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)
