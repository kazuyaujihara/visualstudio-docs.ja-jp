---
title: IDebugAsyncOperation インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugAsyncOperation interface
ms.assetid: ebb2ea75-1443-4d8a-812d-171a166f5f9d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 820ecc40924ace4153b76f46c8b8fd1603512ebb
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58150817"
---
# <a name="idebugasyncoperation-interface"></a>IDebugAsyncOperation インターフェイス
プロセス デバッグ マネージャーの実装、`IDebugAsyncOperation`インターフェイス。 言語エンジンを呼び出して、`IDebugApplication::CreateAsyncDebugOperation`このインターフェイスへの参照を取得します。 言語エンジンを使用できる、`IDebugAsyncOperation`同期デバッグ操作への非同期アクセスを提供するインターフェイス。  
  
 継承されたメソッドだけでなく`IUnknown`、`IDebugAsyncOperation`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugAsyncOperation::GetSyncDebugOperation](../../winscript/reference/idebugasyncoperation-getsyncdebugoperation.md)|このオブジェクトに関連付けられている同期デバッグ操作を返します。|  
|[IDebugAsyncOperation::Start](../../winscript/reference/idebugasyncoperation-start.md)|非同期の操作が開始されます。|  
|[IDebugAsyncOperation::Abort](../../winscript/reference/idebugasyncoperation-abort.md)|操作をキャンセルします。|  
|[IDebugAsyncOperation::QueryIsComplete](../../winscript/reference/idebugasyncoperation-queryiscomplete.md)|デバッグ操作が完了したかどうかを決定します。|  
|[IDebugAsyncOperation::GetResult](../../winscript/reference/idebugasyncoperation-getresult.md)|同期デバッグ操作から返されたオブジェクトのパラメーターと戻り値を提供します。|