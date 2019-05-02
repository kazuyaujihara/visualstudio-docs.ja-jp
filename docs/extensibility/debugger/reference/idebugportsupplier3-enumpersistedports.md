---
title: IDebugPortSupplier3::EnumPersistedPorts |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
helpviewer_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
ms.assetid: 1c3dead3-5d6c-4067-8418-4015f0b0dd07
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c646974a1d1303482785ffd0240b3374e2ed071f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62871550"
---
# <a name="idebugportsupplier3enumpersistedports"></a>IDebugPortSupplier3::EnumPersistedPorts
このメソッドは、永続化されたポートの一覧を列挙するオブジェクトを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT EnumPersistedPorts(
   BSTR_ARRAY         PortNames,
   IEnumDebugPorts2** ppEnum
);
```

```csharp
int EnumPersistedPorts(
   BSTR_ARRAY           PortNames,
   out IEnumDebugPorts2 ppEnum
);
```

#### <a name="parameters"></a>パラメーター
 `PortNames`

 [in]A [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md)を検索して永続化されたポートで返すポート名の一覧を含む構造体。 これらの名前で保存されるポートだけが返されます。

 `ppEnum`

 [out]実装するオブジェクト、 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)インターフェイス。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 ポート サプライヤーのインスタンス化、およびポート サプライヤーが破棄されるときに保存するときに、永続化されたポートが読み込まれます。

## <a name="see-also"></a>関連項目
- [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)
- [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)
- [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md)