---
title: IDebugSourceServerModule |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSourceServerModule interface
ms.assetid: 38213060-451d-46e6-8b4a-efc123e01a2c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5bb686ff492ca836d35b21d54298876314ecb8d5
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66321923"
---
# <a name="idebugsourceservermodule"></a>IDebugSourceServerModule
PDB ファイルに含まれるソース サーバーの情報を表します。

## <a name="syntax"></a>構文

```
IDebugSourceServerModule : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 このインターフェイスはデバッガー エンジンによって実装され、デバッガー UI によって使用します。

## <a name="methods"></a>メソッド
 次の表は、メソッドの`IDebugSourceServerModule`します。

|メソッド|説明|
|------------|-----------------|
|[GetSourceServerData](../../../extensibility/debugger/reference/idebugsourceservermodule-getsourceserverdata.md)|ソース サーバーの情報の配列を取得します。|

## <a name="requirements"></a>必要条件
 ヘッダー:Msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll