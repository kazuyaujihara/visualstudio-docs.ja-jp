---
title: IPropertyProxyEESide::InitSourceDataProvider |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::InitSourceDataProvider
helpviewer_keywords:
- IPropertyProxyEESide::InitSourceDataProvider
ms.assetid: 5156f593-5052-4e3a-9d02-081916fb342d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6fb0d2b960c2bafd1a2d502e41c8a435a5205d11
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62865772"
---
# <a name="ipropertyproxyeesideinitsourcedataprovider"></a>IPropertyProxyEESide::InitSourceDataProvider
このオブジェクトのソース データを初期化し、初期のデータを格納するオブジェクトを返します。

## <a name="syntax"></a>構文

```cpp
HRESULT InitSourceDataProvider(
   IEEDataStorage** dataOut
);
```

```csharp
int InitSourceDataProvider(
   out IEEDataStorage dataOut
);
```

#### <a name="parameters"></a>パラメーター
 `dataOut`

 [out]返します、 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)オブジェクト

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドが返すことができますので、オブジェクトを初期化するために必要なことすべて、 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)オブジェクトのデータのインターフェイス。 これにより、オブジェクトのデータを表示および、許可されている場合は、型のビジュアライザーによって変更できます。

## <a name="see-also"></a>関連項目
- [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)