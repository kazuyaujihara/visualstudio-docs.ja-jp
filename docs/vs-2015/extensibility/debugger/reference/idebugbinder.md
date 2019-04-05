---
title: IDebugBinder |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugBinder
helpviewer_keywords:
- IDebugBinder interface
ms.assetid: d1f31e5b-c6e2-4e02-8959-b3e86041b29c
caps.latest.revision: 17
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e7f5d1e6786d0d774b658484cf833eee269a1453
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58972817"
---
# <a name="idebugbinder"></a>IDebugBinder
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015 での式エバリュエーターの実装には、この方法は非推奨とされます。 CLR 式エバリュエーターの実装方法の詳細についてを参照してください[CLR 式エバリュエーター](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)と[マネージ式エバリュエーターのサンプル](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)します。  
  
 このインターフェイスは、通常、メモリのコンテキストまたはシンボルの現在の値を格納しているオブジェクトをシンボル プロバイダーによって返されるシンボル フィールドをバインドします。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugBinder : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 このインターフェイスは、式の評価をサポートし、デバッグ エンジン (DE) によって実装する必要があります。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 このインターフェイスは式の評価プロセスで使用し、通常の実装で使用[EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)と[EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 次の表は、メソッドの`IDebugBinder`します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[Bind](../../../extensibility/debugger/reference/idebugbinder-bind.md)|メモリのコンテキストまたはシンボルの現在の値を格納しているオブジェクトを取得します。|  
|[ResolveRuntimeType](../../../extensibility/debugger/reference/idebugbinder-resolveruntimetype.md)|オブジェクトの実行時の型を決定します。|  
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugbinder-getmemorycontext.md)|メモリ コンテキスト オブジェクトの場所またはメモリ アドレスに変換します。|  
|[GetFunctionObject](../../../extensibility/debugger/reference/idebugbinder-getfunctionobject.md)|取得、 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)関数のパラメーターを作成するために使用するオブジェクト。|  
|[ResolveDynamicType](../../../extensibility/debugger/reference/idebugbinder-resolvedynamictype.md)|変数の正確な型を取得します。|  
  
## <a name="remarks"></a>Remarks  
 このインターフェイスでの式エバリュエーターで使用されるオブジェクトの解析ツリーを返します。 式エバリュエーターが式内のシンボルのインスタンスに変換するシンボル プロバイダーを使用して式を解析[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)、その型およびソース コード内の場所には、各シンボルをについて説明します。 [バインド](../../../extensibility/debugger/reference/idebugbinder-bind.md)メソッドに変換します`IDebugField`オブジェクトを[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)接続またはシンボルをバインドするオブジェクトをメモリ内の実際の値を入力します。 これら`IDebugObject`オブジェクトは、後で評価の解析ツリーに保存されます。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: ee.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [式の評価のインターフェイス](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)
