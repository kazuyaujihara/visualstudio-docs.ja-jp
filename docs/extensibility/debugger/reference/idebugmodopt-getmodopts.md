---
title: IDebugModOpt::GetModOpts |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugModOpt::GetModOpts
- GetModOpts
ms.assetid: cb513fa9-d521-4a65-b968-f55f53a368df
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f5ebced053b80af8dce81d41e6614e89e4ffbf3a
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66324007"
---
# <a name="idebugmodoptgetmodopts"></a>IDebugModOpt::GetModOpts
オプションの修飾子の一覧を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetModOpts(
   ULONG  celt,
   BSTR*  rgelt,
   ULONG* pceltFetched
);
```

```csharp
int GetModOpts(
   uint         celt,
   out string[] rgelt,
   ref uint     pceltFetched
);
```

## <a name="parameters"></a>パラメーター
`celt`\
[in]返される要素の数。

`rgelt`\
[out]オプションを含む配列を返します。

`pceltFetched`\
[入力、出力]返される要素の数、`rgelt`配列。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugModOpt](../../../extensibility/debugger/reference/idebugmodopt.md)