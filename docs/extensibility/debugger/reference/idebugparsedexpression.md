---
title: IDebugParsedExpression |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugParsedExpression
helpviewer_keywords:
- IDebugParsedExpression interface
ms.assetid: be6486ed-b070-4898-95b1-58581bcb4447
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5549b2c86df77907fd92bc2948deaa36fdceb353
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703423"
---
# <a name="idebugparsedexpression"></a>IDebugParsedExpression
> [!IMPORTANT]
>  Visual Studio 2015 での式エバリュエーターの実装には、この方法は非推奨とされます。 CLR 式エバリュエーターの実装方法の詳細についてを参照してください[CLR 式エバリュエーター](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)と[マネージ式エバリュエーターのサンプル](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)します。

 このインターフェイスは、すぐに評価できる解析された式を表します。

## <a name="syntax"></a>構文

```
IDebugParsedExpression : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 式エバリュエーターでは、評価の準備が整った解析された式を表すためには、このインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元のノート
 呼び出し[解析](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)このインターフェイスを返します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、メソッドの`IDebugParsedExpression`します。

|メソッド|説明|
|------------|-----------------|
|[EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)|解析された式を評価します。|

## <a name="remarks"></a>Remarks
 呼び出す、呼び出し元の式を評価する準備ができたら[EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)を返す、 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)評価の結果を格納しています。 この 2 つの部分には、評価、評価、により、解析された式を複数回評価し、解析、式を解析の時間のかかるプロセスをバイパスするアプローチが。

## <a name="requirements"></a>必要条件
 ヘッダー: ee.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [Parse](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)
- [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)