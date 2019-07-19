---
title: IDebugFunctionObject::CreateArrayObject |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugFunctionObject::CreateArrayObject
helpviewer_keywords:
- IDebugFunctionObject::CreateArrayObject method
ms.assetid: a380e53c-15f1-401f-927f-f366eea789e6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 53c1961eb1ed72580fc314d7a1542ddc926780f9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68205820"
---
# <a name="idebugfunctionobjectcreatearrayobject"></a>IDebugFunctionObject::CreateArrayObject
配列オブジェクトを作成します。 この配列は、いずれかのプリミティブ型を含めることがまたはオブジェクトのインスタンスの値。

## <a name="syntax"></a>構文

```cpp
HRESULT CreateArrayObject( 
   OBJECT_TYPE    ot,
   IDebugField*   pClassField,
   DWORD          dwRank,
   DWORD          dwDims[],
   DWORD          dwLowBounds[],
   IDebugObject** ppObject
);
```

```csharp
int CreateArrayObject(
   enum_OBJECT_TYPE ot,
   IDebugField      pClassField,
   uint             dwRank,
   uint[]           dwDims,
   uint[]           dwLowBounds,
   out IDebugObject ppObject
);
```

#### <a name="parameters"></a>パラメーター
 `ot`

 [in]値を指定します、 [OBJECT_TYPE](../../../extensibility/debugger/reference/object-type.md)新しい配列のオブジェクトの種類を示す列挙値。

 `pClassField`

 [in][IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インスタンスの値オブジェクトの配列を作成する場合に、オブジェクトのクラスを表すオブジェクト。 プリミティブ オブジェクトの配列を作成するには、このパラメーターは null 値を使用します。

 `dwRank`

 [in]ランクまたは配列の次元数。

 `dwDims`

 [in]配列の各次元のサイズ。

 `dwLowBounds`

 [in]各次元の配信元 (通常は 0 または 1)。

 `ppObject`

 [out]返します、 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)新しく作成された配列を表すオブジェクト。 これは、実際には、 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)オブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 によって表される関数への配列パラメーターを表すオブジェクトを作成するには、このメソッドを呼び出して、 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)インターフェイス。

## <a name="see-also"></a>関連項目
- [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)