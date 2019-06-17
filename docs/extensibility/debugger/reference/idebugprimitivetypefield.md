---
title: IDebugPrimitiveTypeField |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPrimitiveTypeField interface
ms.assetid: 73a428fd-797e-4ceb-8392-ba16f1c5226b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4012b919cffc5e16433567fac283ac731d4d215c
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353279"
---
# <a name="idebugprimitivetypefield"></a>IDebugPrimitiveTypeField
プリミティブ型の列挙値を表す、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インターフェイス。

## <a name="syntax"></a>構文

```
IDebugPrimitiveTypeField : IDebugField
```

## <a name="methods"></a>メソッド
 メソッドだけでなく、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)インターフェイスでは、このインターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|[GetPrimitiveType](../../../extensibility/debugger/reference/idebugprimitivetypefield-getprimitivetype.md)|このフィールドに関連付けられているプリミティブ型を取得します。|

## <a name="requirements"></a>必要条件
 ヘッダー:Sh.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll