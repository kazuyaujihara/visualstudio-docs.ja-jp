---
title: IEnumDebugFields::Next |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugFields::Next
helpviewer_keywords:
- IEnumDebugFields::Next method
ms.assetid: 22c177a2-af81-4234-812b-f9b47be245a2
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ee2cc5273b5ec47f99916a308312f6d26c718033
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350427"
---
# <a name="ienumdebugfieldsnext"></a>IEnumDebugFields::Next
このメソッドは、列挙体から次の要素のセットを返します。

## <a name="syntax"></a>構文

```cpp
HRESULT Next(
   ULONG         celt,
   IDebugField** rgelt,
   ULONG*        pceltFetched
);
```

```csharp
int Next(
   uint          celt,
   IDebugField[] rgelt,
   ref uint      pceltFetched
);
```

## <a name="parameters"></a>パラメーター
`celt`\
[in]取得する要素の数。 最大サイズを指定します、`rgelt`配列。

`rgelt`\
[入力、出力]配列[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)情報を格納する要素。

`pceltFetched`\
[out]実際に返される要素の数を返します`rgelt`します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`返される可能性があります、要求された要素数よりも少ない場合、それ以外の場合、エラー コードを返します。

## <a name="see-also"></a>関連項目
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)