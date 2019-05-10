---
title: IDebugProviderProgramNode2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProviderProgramNode2
helpviewer_keywords:
- IDebugProviderProgramNode2
ms.assetid: f0bca1cc-afbe-44cf-b5aa-d078aa685d24
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1f9e0756c3cb9e92d0899020383d536b83892046
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458756"
---
# <a name="idebugproviderprogramnode2"></a>IDebugProviderProgramNode2
このインターフェイスでは、プロセス境界をまたいでプログラム関連のインターフェイスをマーシャ リングします。

## <a name="syntax"></a>構文

```
IDebugProviderProgramNode2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 デバッグ エンジン (DE) を実装する同一のオブジェクトにこのインターフェイスを実装する[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)プロセスの境界を越えてマーシャ リングのインターフェイスをサポートするためにします。

## <a name="notes-for-callers"></a>呼び出し元のノート
 呼び出す[QueryInterface](/cpp/atl/queryinterface)上、`IDebugProgramNode2`をこのインターフェイスを取得するインターフェイス。 このインターフェイスを取得できない場合、DE にはインターフェイスのマーシャ リングはサポートされません。

## <a name="methods-in-vtable-order"></a>Vtable 順序メソッド
 このインターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|[UnmarshalDebuggeeInterface](../../../extensibility/debugger/reference/idebugproviderprogramnode2-unmarshaldebuggeeinterface.md)|プロセスの境界を越えて、指定したインターフェイスを取得します。|

## <a name="remarks"></a>Remarks
 デバッグ中のプログラムから別のプロセス領域で、DE を実行すると、このインターフェイスは実装: デバッグ中のプログラムのプロセス空間ではなく、Visual Studio のプロセス領域で、DE が実行されている場合などです。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)