---
title: IActiveScript::Close |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.Close
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_Close
ms.assetid: cc7dd63b-1d7e-410a-857b-09ea3aade275
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 53b71471ada55751de301391fdcc70387c1bb6c2
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58157050"
---
# <a name="iactivescriptclose"></a>IActiveScript::Close
により、スクリプト エンジンは、現在読み込まれているスクリプトの破棄の状態が失われるおよび closed の状態を入力するため、他のオブジェクトが任意のインターフェイス ポインターを解放します。 イベント シンク、すぐに実行されたスクリプトのテキスト、および実行中のマクロの呼び出しが完了した後、状態の変更 (を使用して、 [iactivescript::interruptscriptthread](../../winscript/reference/iactivescript-interruptscriptthread.md)実行中のスクリプト スレッドをキャンセルする)。 循環参照の問題を防ぐために、インターフェイスが解放される前に、作成、ホストによってこのメソッドを呼び出す必要があります。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Close(void);  
```  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|[値]|説明|  
|-----------|-------------|  
|`S_OK`|成功。|  
|`E_UNEXPECTED`|呼び出しが予期されていませんでした (たとえば、スクリプト エンジンが既に終了状態に)。|  
|`OLESCRIPT_S_PENDING`|メソッドが正常にキューに登録が状態がまだ変更されていません。 状態の変更、サイトが場合にコールバックする、 [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md)メソッド。|  
|`S_FALSE`|メソッドが成功しましたが、スクリプトは既に終了されています。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)