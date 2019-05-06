---
title: IDebugArrayField |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayField
helpviewer_keywords:
- IDebugArrayField interface
ms.assetid: 9667b0a5-4295-46cc-9388-b75c1350be15
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a0eb59553196b6397f7c222c4fc8d0eae048012d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62924006"
---
# <a name="idebugarrayfield"></a>IDebugArrayField
このインターフェイスには、シンボルの配列または型について説明します。

## <a name="syntax"></a>構文

```
IDebugArrayField : IDebugContainerField
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 シンボル プロバイダーを実装する同一のオブジェクトにこのインターフェイスを実装する、 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)インターフェイス。 このインターフェイスは、配列オブジェクトを表す特殊化です。

## <a name="notes-for-callers"></a>呼び出し元のノート
 使用[QueryInterface](/cpp/atl/queryinterface)からこのインターフェイスを取得する、 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)インターフェイスの場合は[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)フラグを返します`FIELD_TYPE_ARRAY`します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 メソッドだけでなく、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)と[IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)インターフェイスでは、このインターフェイスは、次を実装します。

|メソッド|説明|
|------------|-----------------|
|[GetNumberOfElements](../../../extensibility/debugger/reference/idebugarrayfield-getnumberofelements.md)|配列内の要素の数を取得します。|
|[GetElementType](../../../extensibility/debugger/reference/idebugarrayfield-getelementtype.md)|配列内の要素の型を取得します。|
|[GetRank](../../../extensibility/debugger/reference/idebugarrayfield-getrank.md)|配列のランクを取得します。|

## <a name="requirements"></a>必要条件
 ヘッダー: sh.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [シンボルプロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)