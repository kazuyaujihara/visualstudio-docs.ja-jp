---
title: IDebugEnumField |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEnumField
helpviewer_keywords:
- IDebugEnumField interface
ms.assetid: 42f685bf-0f39-47f4-98b0-6022efe2bf97
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 14ea4834619d9e28d4b8a15206b3ea9411f50017
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345106"
---
# <a name="idebugenumfield"></a>IDebugEnumField
このインターフェイスは、列挙型を表します。

## <a name="syntax"></a>構文

```
IDebugEnumField : IDebugContainerField
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 シンボル プロバイダーは、列挙体を表すためには、このインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元のノート
 使用[QueryInterface](/cpp/atl/queryinterface)からこのインターフェイスを取得する、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インターフェイスの場合は[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)返します`FIELD_TYPE_ENUM`します。

## <a name="methods-in-vtable-order"></a>VTable 順序メソッド
 メソッドだけでなく、`IDebugField`と`IDebugContainerField`インターフェイスでは、このインターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|[GetUnderlyingSymbol](../../../extensibility/debugger/reference/idebugenumfield-getunderlyingsymbol.md)|返します、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)この列挙型の名前を記述します。|
|[GetStringFromValue](../../../extensibility/debugger/reference/idebugenumfield-getstringfromvalue.md)|指定された値に関連付けられた列挙定数の名前を返します。|
|[GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)|指定された列挙定数の名前に関連付けられた値を返します|
|[GetValueFromStringCaseInsensitive](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstringcaseinsensitive.md)|指定された列挙定数の名前が無視する場合に関連付けられている値を返します。|

## <a name="remarks"></a>Remarks
 基になるシンボルの場所に実際にバインドされている[バインド](../../../extensibility/debugger/reference/idebugbinder-bind.md)します。

## <a name="requirements"></a>必要条件
 ヘッダー: sh.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [シンボルプロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [Bind](../../../extensibility/debugger/reference/idebugbinder-bind.md)