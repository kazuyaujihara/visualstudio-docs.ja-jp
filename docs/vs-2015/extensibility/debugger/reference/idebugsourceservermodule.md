---
title: IDebugSourceServerModule |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSourceServerModule interface
ms.assetid: 38213060-451d-46e6-8b4a-efc123e01a2c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0dec9408d0cd1907a533a8cabe740832fe652398
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62555697"
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