---
title: IDebugPointerObject::Dereference |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerObject::Dereference
helpviewer_keywords:
- IDebugPointerObject::Dereference method
ms.assetid: 196ec2cc-8569-4780-b217-23b24e7f50ca
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f01e863d03f6179ef4c15f50521cc72ba21f5740
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706588"
---
# <a name="idebugpointerobjectdereference"></a>IDebugPointerObject::Dereference
指すオブジェクトを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT DeReference( 
   DWORD          dwIndex,
   IDebugObject** ppObject
);
```

```csharp
int Dereference(
   uint             dwIndex,
   out IDebugObject ppObject
);
```

#### <a name="parameters"></a>パラメーター
 `dwIndex`

 [in]オブジェクトの先頭からの単純なバイト オフセットが指すになりました。

 `ppObject`

 [out]返します、 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)存在する場合、オブジェクトを表す、指すし、オフセットのオブジェクトします。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。 このオブジェクトが別のオブジェクトを指していない場合は、E_FAIL を返します。

## <a name="remarks"></a>Remarks
 指すオブジェクトには、プリミティブ型またはクラスまたは構造体などのより複雑な型を使用できます。

## <a name="see-also"></a>関連項目
- [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)