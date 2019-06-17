---
title: IDebugPortSupplierEx2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPortSupplierEx2 interface
ms.assetid: dae0050a-a50a-4f35-bfbd-e538f537b20f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3bebf232e17df54d4dae2392a40f2ccbc3fc711c
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353314"
---
# <a name="idebugportsupplierex2"></a>IDebugPortSupplierEx2
選択し、コア サーバーと通信のポート サプライヤーのサポートを提供します。

## <a name="syntax"></a>構文

```
IDebugPortSupplierEx2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 使用するコア サーバーを選択できるように、カスタム ポート サプライヤーはこのインターフェイスを実装します。

## <a name="methods"></a>メソッド
 次の表は、メソッドの**IDebugPortSupplierEx2**します。

|メソッド|説明|
|------------|-----------------|
|[SetServer](../../../extensibility/debugger/reference/idebugportsupplierex2-setserver.md)|ポート サプライヤーのコア サーバーを設定します。|

## <a name="requirements"></a>必要条件
 ヘッダー:Portpriv.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
- [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)