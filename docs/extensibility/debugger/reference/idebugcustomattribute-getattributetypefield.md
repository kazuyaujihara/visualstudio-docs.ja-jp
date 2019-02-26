---
title: IDebugCustomAttribute::GetAttributeTypeField |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttribute::GetAttributeTypeField
helpviewer_keywords:
- IDebugCustomAttribute::GetAttributeTypeField
ms.assetid: d6ce26d5-42ba-44c1-8659-0516db5bc82d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cbbf0d91b344f1a45eb09d480eb631ac1a159046
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56722786"
---
# <a name="idebugcustomattributegetattributetypefield"></a>IDebugCustomAttribute::GetAttributeTypeField
カスタム属性クラスの型を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetAttributeTypeField( 
   IDebugClassField** ppCAType
);
```

```csharp
int GetAttributeTypeField(
   out IDebugClassField ppCAType
);
```

#### <a name="parameters"></a>パラメーター
 `ppCAType`

 [out]返します、 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)カスタム属性がインスタンス クラスを表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 カスタム属性は、常にクラスです。 このメソッドへのアクセスを提供する、 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)そのクラスを記述するオブジェクト。

## <a name="see-also"></a>関連項目
- [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)