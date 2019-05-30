---
title: IDebugField::GetKind |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField::GetKind
helpviewer_keywords:
- IDebugField::GetKind method
ms.assetid: e7c9c60a-8e55-4ecc-aa63-0c814a1e92cc
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d99c7d1bed9f5afe844539c9a9ccab11f43a8002
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66333181"
---
# <a name="idebugfieldgetkind"></a>IDebugField::GetKind
このメソッドは、フィールドの種類を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetKind( 
   FIELD_KIND* pdwKind
);
```

```csharp
int GetKind(
   out enum_FIELD_KIND pdwKind
);
```

## <a name="parameters"></a>パラメーター
`pdwKind`\
[out]フィールドの種類を返しますの組み合わせとして[FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)定数。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)