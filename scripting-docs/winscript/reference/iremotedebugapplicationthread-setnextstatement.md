---
title: 'IRemoteDebugApplicationThread:: SetNextStatement |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationThread.SetNextStatement
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplicationThread::SetNextStatement
ms.assetid: 356766da-f7b7-4e8d-b4f3-2ab8da0609b8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 71e690d0e5b7567aabc88aabde907b67517f12aa
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575508"
---
# <a name="iremotedebugapplicationthreadsetnextstatement"></a>IRemoteDebugApplicationThread::SetNextStatement
指定されたフレームのコンテキストで、指定されたコードコンテキストにできるだけ近いうちに実行を継続します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetNextStatement(  
   IDebugStackFrame*   pStackFrame,  
   IDebugCodeContext*  pCodeContext  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pStackFrame`  
 からスタックフレームオブジェクト。 この引数は NULL にすることができます。これは、現在のスタックフレームが使用されることを意味します。  
  
 `pCodeContext`  
 からコードコンテキスト。 この引数は NULL にすることができます。これは、現在のコードコンテキストを使用する必要があることを意味します。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、`pStackFrame` によって指定されたフレームのコンテキストで、`pCodeContext` によって指定されたコードコンテキストにできるだけ近づけるように実行を強制します。 これらの引数のいずれかが、現在のフレームまたはコンテキストを表す `NULL` である可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [IRemoteDebugApplicationThread インターフェイス](../../winscript/reference/iremotedebugapplicationthread-interface.md)