---
title: IDebugTypeFieldBuilder2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugTypeFieldBuilder2 interface
ms.assetid: 23911c5b-2bbf-4734-9976-87a0bd6ea36c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a22f8d60318721fbb51e0d5be7965c27666b8c48
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66319759"
---
# <a name="idebugtypefieldbuilder2"></a>IDebugTypeFieldBuilder2
拡張、 **IDebugTypeFieldBuilder**配列型を作成できるようにします。

## <a name="syntax"></a>構文

```
IDebugTypeFieldBuilder2 : IDebugTypeFieldBuilder
```

## <a name="notes-for-callers"></a>呼び出し元のノート
 このインターフェイスは、シンボル プロバイダーから取得できます。

## <a name="methods"></a>メソッド
 メソッドだけでなく、 [IDebugTypeFieldBuilder](../../../extensibility/debugger/reference/idebugtypefieldbuilder.md)インターフェイスでは、このインターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|[CreateArrayOfType](../../../extensibility/debugger/reference/idebugtypefieldbuilder2-createarrayoftype.md)|指定された種類とサイズの配列を作成します。|

## <a name="requirements"></a>必要条件
 ヘッダー:Sh.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll