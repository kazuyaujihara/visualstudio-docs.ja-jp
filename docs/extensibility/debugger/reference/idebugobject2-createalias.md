---
title: IDebugObject2::CreateAlias |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2::CreateAlias
helpviewer_keywords:
- IDebugObject2::CreateAlias method
ms.assetid: 54a05920-5d13-4f67-962b-d1a7f013dff9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b2463095269103bcc6d2387451b4474af70698d9
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66202369"
---
# <a name="idebugobject2createalias"></a>IDebugObject2::CreateAlias
一意の ID またはこのオブジェクトの別名を作成します。 または、既存のエイリアスを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT CreateAlias(
   IDebugAlias** ppAlias
);
```

```csharp
int CreateAlias(
   out IDebugAlias ppAlias
);
```

## <a name="parameters"></a>パラメーター
`ppAlias`\
[out]新しい (または既存) のエイリアスです。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 エイリアスは、オブジェクトがメモリ内にある間は、特定のオブジェクトを表すラベルです。

## <a name="see-also"></a>関連項目
- [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)