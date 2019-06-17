---
title: IDebugPortPicker::SetSite |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPortPicker::SetSite
ms.assetid: 7319e187-adfe-4b3f-aec9-521356fb5a8a
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 33d6d12bd21a6ab208fed019c1e0f763bce86724
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66340359"
---
# <a name="idebugportpickersetsite"></a>IDebugPortPicker::SetSite
サービス プロバイダーを設定します。

## <a name="syntax"></a>構文

```cpp
HRESULT SetSite(
   IServiceProvider * pSP
);
```

```csharp
public int SetSite(
   IServiceProvider pSP
);
```

## <a name="parameters"></a>パラメーター
`pSP`\
[in]サービス プロバイダーのインターフェイスへの参照。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドが、他のメソッドが呼び出される前に呼び出されます。

## <a name="see-also"></a>関連項目
- [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)