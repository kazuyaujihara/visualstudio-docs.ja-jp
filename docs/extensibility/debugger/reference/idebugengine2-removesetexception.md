---
title: IDebugEngine2::RemoveSetException |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::RemoveSetException
helpviewer_keywords:
- IDebugEngine2::RemoveSetException
ms.assetid: bdd25097-0e9d-4218-b417-0497ea48d2e8
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 45c3cec5ab0511ea80a6b04d9b3ee575afd9d149
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66352548"
---
# <a name="idebugengine2removesetexception"></a>IDebugEngine2::RemoveSetException
不要になったデバッグ エンジンによって処理されるように指定された例外を削除します。

## <a name="syntax"></a>構文

```cpp
HRESULT RemoveSetException( 
   EXCEPTION_INFO* pException
);
```

```csharp
int RemoveSetException( 
   EXCEPTION_INFO[] pException
);
```

## <a name="parameters"></a>パラメーター
`pException`\
[in][EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)を削除する例外を記述する構造体。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 例外を削除する必要があります設定されている以前に以前の呼び出しによって、 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)メソッド。

 セットのすべての例外を一度に削除するには、呼び出し、 [RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md)メソッド。

## <a name="see-also"></a>関連項目
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)