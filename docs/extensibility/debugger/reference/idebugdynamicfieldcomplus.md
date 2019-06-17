---
title: IDebugDynamicFieldCOMPlus |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugDynamicFieldCOMPlus interface
ms.assetid: c3a25f27-327a-4bdb-b026-27d436ddcd0c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 824498f3d7657bcc5984d31a1abaa4e97c4a9a7d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66330200"
---
# <a name="idebugdynamicfieldcomplus"></a>IDebugDynamicFieldCOMPlus
動的フィールドを表す、 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)オブジェクト。

## <a name="syntax"></a>構文

```
IDebugDynamicFieldCOMPlus : IDebugDynamicField
```

## <a name="methods"></a>メソッド
 メソッドだけでなく、 [IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md)インターフェイスでは、このインターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|[GetTypeFromPrimitive](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus-gettypefromprimitive.md)|プリミティブ型を指定する型を取得します。|
|[GetTypeFromTypeDef](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus-gettypefromtypedef.md)|そのトークンを指定する型を取得します。|

## <a name="requirements"></a>必要条件
 ヘッダー:Sh.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll