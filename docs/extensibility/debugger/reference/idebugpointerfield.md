---
title: IDebugPointerField |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerField
helpviewer_keywords:
- IDebugPointerField interface
ms.assetid: d51bd5b2-f18e-4e27-b4fb-e6f652fbf635
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ff3ed7d23272bad1e047ddca46e20b4710644e30
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56704450"
---
# <a name="idebugpointerfield"></a>IDebugPointerField
このインターフェイスは、ポインター型を表します。

## <a name="syntax"></a>構文

```
IDebugPointerField : IDebugContainerField
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 シンボル プロバイダーは、ポインターを表すためには、このインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元のノート
 使用[QueryInterface](/cpp/atl/queryinterface)からこのインターフェイスを取得する、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インターフェイスの場合は[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)返します`FIELD_TYPE_POINTER`します。

## <a name="methods-in-vtable-order"></a>Vtable 順序メソッド
 メソッドだけでなく、`IDebugField`と`IDebugContainerField`インターフェイスでは、このインターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|[GetDereferencedField](../../../extensibility/debugger/reference/idebugpointerfield-getdereferencedfield.md)|返します、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)ポインターのターゲットを記述します。|

## <a name="remarks"></a>Remarks
 C および C++ でのポインターはコンテナーとして配列表記と共に使用する場合。 たとえば、 `char *pString`、`pString`へのポインターの型を持つ`char`します。 `pString[3]` ポインターであるコンテナーの型を持つ`char`そのコンテナーの 4 番目の要素を参照します。

## <a name="requirements"></a>必要条件
 ヘッダー: sh.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [シンボルプロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)