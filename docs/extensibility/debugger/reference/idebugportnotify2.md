---
title: IDebugPortNotify2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortNotify2
helpviewer_keywords:
- IDebugPortNotify2 interface
ms.assetid: 43278b79-bf16-4c08-bcf1-6f7f7a17feab
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2427bfbc70c992cfcd41217aec56aa94d825faae
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56713426"
---
# <a name="idebugportnotify2"></a>IDebugPortNotify2
このインターフェイスは、登録またはで実行されているポートでデバッグできるプログラムの登録を解除します。

## <a name="syntax"></a>構文

```
IDebugPortNotify2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 カスタム ポート サプライヤーは、サポートを追加して、ポートからプログラムを削除するのには、このインターフェイスを実装します。 実装する同一のオブジェクトに通常実装、 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)インターフェイス。

## <a name="notes-for-callers"></a>呼び出し元のノート
 呼び出し[QueryInterface](/cpp/atl/queryinterface)上、`IDebugPort2`インターフェイスは、このインターフェイスを返します。 呼び出しも、 [GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md)このインターフェイスを返します。 デバッグ エンジンは、パラメーターとしてこのインターフェイスを確認できます[WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、メソッドの`IDebugPortNotify2`します。

|メソッド|説明|
|------------|-----------------|
|[AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)|実行されているポートをデバッグできるプログラムを登録します。|
|[RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)|実行されているポートからデバッグできるプログラムを登録解除します。|

## <a name="remarks"></a>Remarks
 デバッグ ポートに、プログラムはロードまたはアンロードを知る方法がない限り、カスタム ポート サプライヤーはこのインターフェイスを実装する必要があります。 このインターフェイスを使用して、特定のポートを使用して、デバッグ用に読み込まれたすべてのプログラムが追跡されます。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)