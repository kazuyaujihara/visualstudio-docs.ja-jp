---
title: IDebugEngine3::LoadSymbols |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine3::LoadSymbols
helpviewer_keywords:
- IDebugEngine3::LoadSymbols
ms.assetid: c846a440-1d91-4d48-b8f1-82e902ae152b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 72c4fce5a7e8dd53093e21db2771d2176462e67c
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66352521"
---
# <a name="idebugengine3loadsymbols"></a>IDebugEngine3::LoadSymbols
このデバッグ エンジンでデバッグ中のすべてのモジュールのシンボルを読み込みます (必要に応じて)。

## <a name="syntax"></a>構文

```cpp
HRESULT LoadSymbols();
```

```csharp
int LoadSymbols();
```

## <a name="parameters"></a>パラメーター
 なし。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。エラー コードを返しますそれ以外の場合。

## <a name="remarks"></a>Remarks
 これには、このデバッグ エンジンによって参照されるすべてのモジュールのデバッグ シンボルが読み込まれます。 既に読み込まれていない場合にのみ、シンボルが読み込まれます。 呼び出して設定パスでシンボルが検索されます[SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)します。

## <a name="see-also"></a>関連項目
- [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)
- [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)