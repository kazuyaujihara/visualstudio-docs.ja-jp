---
title: IDebugCoreServer2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer2
helpviewer_keywords:
- IDebugCoreServer2 interface
ms.assetid: 9c47d0a6-9eb1-464e-bd44-fa2b552d4d36
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1f4f01bb8e86e733bef3940a4772f52b28080628
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62922088"
---
# <a name="idebugcoreserver2"></a>IDebugCoreServer2
このインターフェイスを表し、ネットワーク上のコンピューター上のサーバーからの情報の取得に使用されます。

## <a name="syntax"></a>構文

```
IDebugCoreServer2 : IUknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 Visual Studio では、サーバーを表すためには、このインターフェイスを実装します。 Visual Studio の各インスタンスは、このインターフェイスのインスタンスを作成します。

## <a name="notes-for-callers"></a>呼び出し元のノート
 カスタム ポート サプライヤーへの呼び出しでこのインターフェイスの受信[イベント](../../../extensibility/debugger/reference/idebugportevents2-event.md)します。

 デバッグ エンジンとして使用できるは、このインターフェイスへの呼び出しを通じて間接的に[GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md) (返された[IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)、インターフェイスから派生した`IDebugCoreServer2`)。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、メソッドの`IDebugCoreServer2`します。

|メソッド|説明|
|------------|-----------------|
|[GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)|マシンの属性と名前を取得します。|
|[GetMachineName](../../../extensibility/debugger/reference/idebugcoreserver2-getmachinename.md)|コンピューターの名前を取得します。|
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)|コンピューター上に存在するポートのサプライヤーを取得します。|
|[GetPort](../../../extensibility/debugger/reference/idebugcoreserver2-getport.md)|コンピューターに既に存在するポートを取得します。|
|[EnumPorts](../../../extensibility/debugger/reference/idebugcoreserver2-enumports.md)|コンピューター上のすべてのポートの列挙子を作成します。|
|[EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)|コンピューター上のすべてのポート サプライヤーの列挙子を作成します。|
|[GetMachineUtilities_V7](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineutilities-v7.md)|マシンのマシン ユーティリティを取得します。|

## <a name="remarks"></a>Remarks
 このインターフェイスは、ネットワーク上のマシンで実行されているプロセスを参照する Visual Studio によっても使用されます。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
- [Event](../../../extensibility/debugger/reference/idebugportevents2-event.md)
- [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)
- [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)