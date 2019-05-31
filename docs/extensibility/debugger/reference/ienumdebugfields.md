---
title: IEnumDebugFields |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugFields
helpviewer_keywords:
- IEnumDebugFields interface
ms.assetid: 403c2a51-3ba5-431f-a1dd-2f3b2046c00c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 50d80242ca516c5fa7f3ad297250e25c782664d0
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350378"
---
# <a name="ienumdebugfields"></a>IEnumDebugFields
このインターフェイスを実装するオブジェクトのコレクションを表します、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インターフェイス。

## <a name="syntax"></a>構文

```
IEnumDebugFields : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 このインターフェイスを実装するオブジェクトのセットを指定するシンボル プロバイダーによって実装されます、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インターフェイス。 存在するための標準 COM 列挙型ではないことに注意してください、 [GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)メソッド。

## <a name="notes-for-callers"></a>呼び出し元のノート
 このインターフェイスは、によって返される[GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)と[GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)します。

## <a name="methods-in-vtable-order"></a>Vtable 順序メソッド
 このインターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|[次へ](../../../extensibility/debugger/reference/ienumdebugfields-next.md)|次のセットを取得します。 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)列挙体からのオブジェクト。|
|[Skip](../../../extensibility/debugger/reference/ienumdebugfields-skip.md)|指定されたエントリ数をスキップします。|
|[Reset](../../../extensibility/debugger/reference/ienumdebugfields-reset.md)|最初のエントリを列挙型をリセットします。|
|[Clone](../../../extensibility/debugger/reference/ienumdebugfields-clone.md)|現在の列挙体のコピーを取得します。|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)|列挙内のエントリの数を取得します。|

## <a name="remarks"></a>Remarks

## <a name="requirements"></a>必要条件
 ヘッダー: sh.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [シンボルプロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)
- [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)