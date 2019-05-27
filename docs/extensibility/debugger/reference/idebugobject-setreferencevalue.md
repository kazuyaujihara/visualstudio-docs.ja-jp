---
title: IDebugObject::SetReferenceValue |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::SetReferenceValue
helpviewer_keywords:
- IDebugObject::SetReferenceValue method
ms.assetid: 08c78a4e-98eb-41cb-8b75-02a6a43d49f7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 7e861a67ada36bd25b30e08bf8a62163bceea979
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66211298"
---
# <a name="idebugobjectsetreferencevalue"></a>IDebugObject::SetReferenceValue
このオブジェクトの参照値を設定します。

## <a name="syntax"></a>構文

```cpp
HRESULT SetReferenceValue( 
   IDebugObject* pObject
);
```

```csharp
int SetReferenceValue(
   [In] IDebugObject pObject
);
```

## <a name="parameters"></a>パラメーター
`pObject`\
[in][IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)新しい参照の値を表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドは、この[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)オブジェクトで指定されたオブジェクトの値への参照、`pObject`パラメーターは、前の参照することになります。 注この`IDebugObject`オブジェクトは参照型に既にあります。

## <a name="see-also"></a>関連項目
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
- [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)