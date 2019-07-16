---
title: 呼び出しスタックの評価 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], call stack evaluation
- call stacks, evaluation
ms.assetid: 373d6b49-0459-4cce-816e-05745a44fe49
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 15fecbc61fec8ba7aa62ca7d79cf11c56b7ce938
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68146414"
---
# <a name="call-stack-evaluation"></a>呼び出し履歴の評価
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

中断モード中に、コール スタックのスタック フレームを表示するために実装する必要があります、 [EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)メソッド。  
  
## <a name="methods-for-evaluation"></a>評価のためのメソッド  
 単純なデバッグ エンジン (DE)、スタック フレームを 1 つだけあります。 中断モード中にスタック フレームを検証するには、次のメソッドを実装する必要があります[IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)|スタック フレームのコードのコンテキストを取得します。 コードのコンテキストでは、スタック フレーム内の現在の命令ポインターを表します。|  
|[GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)|スタック フレームのドキュメント コンテキストを取得します。 ドキュメントのコンテキストでは、スタック フレームのソース コードの現在の場所を表します。 プログラムが停止したときに、ソース コードを表示するために必要です。|  
  
 これらのメソッドでは、いくつかのコンテキストに関連するインターフェイスおよびメソッドの実装が必要です。 したがって、実装する必要があります、 [GetDocumentContext](../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)メソッドと次のメソッドの[IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md)します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetStatementRange](../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)|ドキュメント コンテキストのファイルのステートメントの範囲を取得します。|  
  
 コード コンテキストを列挙するには、すべてのメソッドを実装する必要があります[IEnumDebugCodeContexts2](../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)します。  
  
## <a name="see-also"></a>関連項目  
 [実行の制御と状態の評価](../../extensibility/debugger/execution-control-and-state-evaluation.md)
