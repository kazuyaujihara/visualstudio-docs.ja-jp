---
title: IDebugPropertyField |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPropertyField
helpviewer_keywords:
- IDebugPropertyField interface
ms.assetid: b50edb2c-fb8d-4def-993d-17d23d2027c1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ecaf93a563627306b9fd1ab2e3adad0a83b412ab
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66322706"
---
# <a name="idebugpropertyfield"></a>IDebugPropertyField
このインターフェイスは、取得、およびプロパティを設定できるようにする機能を提供します。

## <a name="syntax"></a>構文

```
IDebugPropertyField : IDebugContainerField
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 シンボル プロバイダーを実装する同一のオブジェクトにこのインターフェイスを実装する、 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)します。 このインターフェイスは、クラスのプロパティの概念をサポートする特殊化です。

## <a name="notes-for-callers"></a>呼び出し元のノート
 使用[QueryInterface](/cpp/atl/queryinterface)からこのインターフェイスを取得する、 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)インターフェイスの場合、 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)メソッドを返します。`FIELD_KIND_PROP`します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 メソッドだけでなく、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)と[IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)インターフェイスでは、このインターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|[GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md)|プロパティを取得するメソッドを取得します。|
|[GetPropertySetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertysetter.md)|プロパティを設定するメソッドを取得します。|

## <a name="remarks"></a>Remarks
 プロパティは、マネージ コードの概念であり、変数として扱われるメソッドを表します。 プロパティは、アンマネージの C++ ではありません。

## <a name="requirements"></a>必要条件
 ヘッダー: sh.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [シンボルプロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)