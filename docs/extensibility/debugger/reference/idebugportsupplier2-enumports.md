---
title: IDebugPortSupplier2::EnumPorts |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortSupplier2::EnumPorts
helpviewer_keywords:
- IDebugPortSupplier2::EnumPorts
ms.assetid: 88b57fd2-eba1-44fa-bd34-cf2ad2b1ff87
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d2e1774df8439adaf7aaaeebf8965b74bf728bb7
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66340195"
---
# <a name="idebugportsupplier2enumports"></a>IDebugPortSupplier2::EnumPorts
ポート サプライヤーによって提供されるすべてのポートの一覧を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT EnumPorts( 
   IEnumDebugPorts2** ppEnum
);
```

```csharp
int EnumPorts( 
   out IEnumDebugPorts2 ppEnum
);
```

## <a name="parameters"></a>パラメーター
`ppEnum`\
[out]返します、 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)指定されたポートの一覧を含むオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
- [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)