---
title: IDebugProgramEngines2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramEngines2
helpviewer_keywords:
- IDebugProgramEngines2 interface
ms.assetid: 53d648f0-6c11-4337-badd-c43f3872b62c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1a5ad34904a2f0bf02e5a2221f1ff73093012a41
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62916931"
---
# <a name="idebugprogramengines2"></a>IDebugProgramEngines2
このインターフェイスは、使用可能なデバッグしたすべてのエンジン (DE) このプログラムをデバッグすることを指定するプログラムのノードによって使用されます。

## <a name="syntax"></a>構文

```
IDebugProgramEngines2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 実装する同一のオブジェクトにこのインターフェイスを実装、DE またはカスタムのポート サプライヤー [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)特定のプログラムに使用する特定のドイツの確立をサポートするためにします。

## <a name="notes-for-callers"></a>呼び出し元のノート
 呼び出す[QueryInterface](/cpp/atl/queryinterface)上、`IDebugProgramNode2`をこのインターフェイスを取得するインターフェイス。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、メソッドの`IDebugProgramEngines2`します。

|メソッド|説明|
|------------|-----------------|
|[EnumPossibleEngines](../../../extensibility/debugger/reference/idebugprogramengines2-enumpossibleengines.md)|このプログラムをデバッグできるすべての DEs を示します。|
|[SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)|このプログラムのデバッグに使用するデバイスを選択します。|

## <a name="remarks"></a>Remarks
 呼び出すことで、[プログラム] ノードでその選択を登録、DE がユーザーによって選択されると、 [SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)します。 選択されたエンジンが、エンジンによって返される[GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)します。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
- [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)