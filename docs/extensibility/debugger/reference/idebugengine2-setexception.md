---
title: IDebugEngine2::SetException |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::SetException
helpviewer_keywords:
- IDebugEngine2::SetException
ms.assetid: e6f5ec48-09e8-4b9b-9dc9-55f8d883f1b7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 288e77ce539a26764a897656c79649720be2438e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56698912"
---
# <a name="idebugengine2setexception"></a>IDebugEngine2::SetException
デバッグ エンジン (DE) を使用して、特定の例外を処理する方法を指定します。

## <a name="syntax"></a>構文

```cpp
HRESULT SetException( 
   EXCEPTION_INFO* pException
);
```

```csharp
int SetException( 
   EXCEPTION_INFO[] pException
);
```

#### <a name="parameters"></a>パラメーター
 `pException`

 [in][EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)それをデバッグする方法と、例外を記述する構造体。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 ファースト チャンス例外を生成するプログラムを停止、2 番目のチャンスをできるように、DE またはまったくありません。

## <a name="see-also"></a>関連項目
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)