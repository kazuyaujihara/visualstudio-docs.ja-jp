---
title: IDebugErrorEvent2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugErrorEvent2
helpviewer_keywords:
- IDebugErrorEvent2 interface
ms.assetid: 275b6f38-b3d4-4cae-8491-491177f524fb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 945b04fc2d5a370ef4b2d17abd90e6bdaa818553
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66327669"
---
# <a name="idebugerrorevent2"></a>IDebugErrorEvent2
このインターフェイスには、ユーザーに報告するエラー メッセージを指定します。

## <a name="syntax"></a>構文

```
IDebugErrorEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 デバッグ エンジン (DE) は、人間が判読できるメッセージとしてエラーを報告するには、このインターフェイスを実装します。 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)このインターフェイスと同じオブジェクトでインターフェイスを実装する必要があります。 SDM を使用して[QueryInterface](/cpp/atl/queryinterface)にアクセスする、`IDebugEvent2`インターフェイス。

## <a name="notes-for-callers"></a>呼び出し元のノート
 デは作成し、エラーを報告するには、このイベント オブジェクトを送信します。 使用して、イベントが送信される、 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)デバッグ中のプログラムに添付するときに、SDM によって指定されたコールバック関数。

## <a name="methods-in-vtable-order"></a>Vtable 順序メソッド
 このインターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|`GetErrorMessage`|人間が判読できる文字列としてエラーを返します。|

## <a name="remarks"></a>Remarks
 デバッグ エンジンには、エラーが発生するは、このインターフェイスを使用して、Visual Studio でメッセージをユーザーに報告することができます。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)