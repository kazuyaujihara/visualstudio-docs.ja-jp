---
title: IEnumDebugCustomAttributes |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumCustomAttributes
helpviewer_keywords:
- IEnumDebugCustomAttributes interface
ms.assetid: 11aa768d-1852-44d6-9de3-17f9bafaded2
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e706999595033ac76508eaa5e3b3f995839ceaea
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66321554"
---
# <a name="ienumdebugcustomattributes"></a>IEnumDebugCustomAttributes
カスタム属性を列挙します。

## <a name="syntax"></a>構文

```
IEnumCustomAttributes : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 シンボル プロバイダーは、カスタム属性をサポートするには、このインターフェイスを実装 (を通じて、 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)インターフェイス)。

## <a name="notes-for-callers"></a>呼び出し元のノート
- [EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)このインターフェイスを返します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、メソッドの`IEnumDebugCustomAttributes`します。

|メソッド|説明|
|------------|-----------------|
|[次へ](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md)|指定された数の列挙体シーケンス内のカスタム属性を取得します。|
|[Skip](../../../extensibility/debugger/reference/ienumdebugcustomattributes-skip.md)|指定された数の列挙体シーケンス内のカスタム属性をスキップします。|
|[Reset](../../../extensibility/debugger/reference/ienumdebugcustomattributes-reset.md)|先頭に、列挙体シーケンスをリセットします。|
|[Clone](../../../extensibility/debugger/reference/ienumdebugcustomattributes-clone.md)|現在の列挙子と同じ列挙状態を格納する列挙子を作成します。|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugcustomattributes-getcount.md)|列挙子では、カスタム属性の数を取得します。|

## <a name="requirements"></a>必要条件
 ヘッダー: sh.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [シンボルプロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)
- [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)