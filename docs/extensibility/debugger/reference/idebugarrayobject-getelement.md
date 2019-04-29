---
title: IDebugArrayObject::GetElement |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetElement
helpviewer_keywords:
- IDebugArrayObject::GetElement method
ms.assetid: 08b44341-7bf1-4a8c-8b79-98ae5785b195
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 735b92bb649344c055f7a645b961925e3cbd4d6e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62924049"
---
# <a name="idebugarrayobjectgetelement"></a>IDebugArrayObject::GetElement
配列の要素を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetElement( 
   DWORD          dwIndex,
   IDebugObject** ppElement
);
```

```csharp
int GetElement(
   [In] uint dwIndex,
   out IDebugObject ppElement
);
```

#### <a name="parameters"></a>パラメーター
 `dwIndex`

 [in]要素のインデックス。

 `ppElement`

 [out]返します、 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)要素を表すインターフェイス。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドは、1 次元の配列として配列オブジェクトが多次元である場合でもすべて配列オブジェクトの要素のように表示されます。 など、配列を指定して`myarray[3][2][6]`と`dwIndex`20 のパラメーターは、このメソッドは、要素から`myarray[1][1][2]`、および`dwIndex`21 のパラメーターは元の要素を返します`myarray[1][1][3]`します。 使用して、 [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md)メソッドを配列の要素の合計数を決定します。

## <a name="see-also"></a>関連項目
- [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)