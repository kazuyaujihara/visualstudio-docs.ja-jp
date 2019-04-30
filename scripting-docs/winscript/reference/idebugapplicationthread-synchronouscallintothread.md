---
title: IDebugApplicationThread::SynchronousCallIntoThread |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationThread.SynchronousCallIntoThread
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplicationThread::SynchronousCallIntoThread
ms.assetid: 8a91157f-dade-418a-ad02-5607ce12c95c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f0c9b89332b55a180220820e8ffe1e030d37a848
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62822087"
---
# <a name="idebugapplicationthreadsynchronouscallintothread"></a>IDebugApplicationThread::SynchronousCallIntoThread
呼び出し元アプリケーションのスレッドでコードを実行するためのメカニズムを提供します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SynchronousCallIntoThread(  
   IDebugThreadCall*  pstcb,  
   DWORD_PTR          dwParam1,  
   DWORD_PTR          dwParam2,  
   DWORD_PTR          dwParam3  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pstcb`  
 [in]呼び出すオブジェクト。  
  
 `dwParam1`  
 [in]最初のパラメーターに渡す、`IDebugThreadCall::ThreadCallHandler`メソッド。  
  
 `dwParam2`  
 [in]2 番目のパラメーターに渡す、`IDebugThreadCall::ThreadCallHandler`メソッド。  
  
 `dwParam3`  
 [in]3 番目のパラメーターに渡す、`IDebugThreadCall::ThreadCallHandler`メソッド。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、呼び出し元が、デバッガー スレッドでコードを実行するためのメカニズムを提供します。 言語エンジンとホストは通常、1 つのスレッドの実装の上に、フリー スレッド オブジェクトを実装するためにこのメソッドを使用します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationThread インターフェイス](../../winscript/reference/idebugapplicationthread-interface.md)   
 [IDebugThreadCall インターフェイス](../../winscript/reference/idebugthreadcall-interface.md)