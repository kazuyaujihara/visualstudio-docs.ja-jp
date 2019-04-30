---
title: 評価コンテキスト |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, context
ms.assetid: 008a20c7-1b27-4013-bf96-d6a3f510da02
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7dae6ddcb0c75f0dcbc2207465aed522a4210159
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63444749"
---
# <a name="evaluation-context"></a>評価コンテキスト
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

> [!IMPORTANT]
> Visual Studio 2015 での式エバリュエーターの実装には、この方法は非推奨とされます。 CLR 式エバリュエーターの実装方法の詳細についてを参照してください[CLR 式エバリュエーター](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)と[マネージ式エバリュエーターのサンプル](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)します。  
  
 デバッグ エンジン (DE) は、式エバリュエーター (EE) を呼び出しに 3 つの引数が渡されます。 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)次の表に示すように、検索と評価のシンボルの状況を判断します。  
  
## <a name="arguments"></a>引数  
  
|引数|説明|  
|--------------|-----------------|  
|`pSymbolProvider`|[IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)記号を識別するために使用するシンボル ハンドラー (SH) を指定するインターフェイス。|  
|`pAddress`|[IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)実行の現在位置を指定するインターフェイス。 これは、実行されているコードを含むメソッドの検索を使用できます。|  
|`pBinder`|[IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)値と型名を指定し、シンボルの検索に使用できるインターフェイス。|  
  
 `IDebugParsedExpression::EvaluateSync` 返します、 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)結果の値とその型を表すインターフェイス。  
  
## <a name="see-also"></a>関連項目  
 [主要なエバリュエーター インターフェイス](../../extensibility/debugger/key-expression-evaluator-interfaces.md)   
 [ローカルの表示](../../extensibility/debugger/displaying-locals.md)   
 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)
