---
title: IDebugProgram2::Terminate |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::Terminate
helpviewer_keywords:
- IDebugProgram2::Terminate
ms.assetid: 4d3127d3-b1e9-4b28-ac22-2f2eea255f86
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 16a6d60173090642bda7d8fd940ecf0699e1d7ec
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66331494"
---
# <a name="idebugprogram2terminate"></a>IDebugProgram2::Terminate
プログラムを終了します。

## <a name="syntax"></a>構文

```cpp
HRESULT Terminate( 
   void 
);
```

```csharp
int Terminate();
```

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 可能であれば、プログラムは終了し、プロセスからアンロードそれ以外の場合、デバッグ エンジン (DE) は、必要なクリーンアップを実行します。

 このメソッドまたは[Terminate](../../../extensibility/debugger/reference/idebugprocess2-terminate.md)メソッドはすべてのデバッグを停止するユーザーへの応答では通常、IDE によって呼び出されます。 このメソッドの実装では、プロセス内でプログラムを終了する必要があります、理想的には、します。 それができない場合、DE する必要がありますプログラムがこのプロセスではこれ以上実行されないように (および必要なクリーンアップを行います)。 場合、`IDebugProcess2::Terminate`メソッドは、IDE によって呼び出された、プロセス全体は終了されてからしばらく、`IDebugProgram2::Terminate`メソッドが呼び出されます。

## <a name="see-also"></a>関連項目
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [Terminate](../../../extensibility/debugger/reference/idebugprocess2-terminate.md)