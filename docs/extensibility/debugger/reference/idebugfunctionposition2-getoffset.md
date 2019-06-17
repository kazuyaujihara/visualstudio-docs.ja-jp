---
title: IDebugFunctionPosition2::GetOffset |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugFunctionPosition2::GetOffset
helpviewer_keywords:
- IDebugFunctionPosition2::GetOffset
ms.assetid: 60943782-aec7-4be2-b222-1984ed53a543
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 891707f5937085f69bf037abdec81e6c36315fa0
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66313322"
---
# <a name="idebugfunctionposition2getoffset"></a>IDebugFunctionPosition2::GetOffset
関数のソース ドキュメント内の位置を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetOffset( 
   TEXT_POSITION* pPosition
);
```

```csharp
int GetOffset(
   TEXT_POSITION[] pPosition
);
```

## <a name="parameters"></a>パラメーター
`pPosition`\
[入力、出力]A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)構造体、関数のドキュメント内の位置が入力されます。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)
- [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)