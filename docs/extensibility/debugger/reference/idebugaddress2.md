---
title: IDebugAddress2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAddress2
helpviewer_keywords:
- IDebugAddress2 interface
ms.assetid: b150e0ed-4ac0-4f8c-9732-4b3e54b9d243
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 10af641162fe9d254eaa3c0c2f5efbf841dc154e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56677644"
---
# <a name="idebugaddress2"></a>IDebugAddress2
このインターフェイスは、このインターフェイスによって表されるアドレスを持つオブジェクトを所有するプロセスの ID へのアクセスを提供します。

## <a name="syntax"></a>構文

```
IDebugAddress2 : IDebugAddress
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 シンボル プロバイダーを実装する同一のオブジェクトにこのインターフェイスを実装する、 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)インターフェイス。 このインターフェイスは、このアドレスに関連付けられているオブジェクトを所有するプロセスの ID へのアクセスを提供します。

## <a name="notes-for-callers"></a>呼び出し元のノート
 使用[QueryInterface](/cpp/atl/queryinterface)からこのインターフェイスを取得する、 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)インターフェイス。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 継承されたメソッドだけでなく、 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)インターフェイスでは、このインターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|[GetProcessID](../../../extensibility/debugger/reference/idebugaddress2-getprocessid.md)|このインターフェイスによって表されるオブジェクトを所有するプロセスの ID を取得します。|

## <a name="requirements"></a>必要条件
 ヘッダー: sh.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [シンボルプロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)