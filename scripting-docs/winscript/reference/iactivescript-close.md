---
title: 'IActiveScript:: Close |Microsoft Docs'
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
ms.openlocfilehash: f858de42ef2948d218aac6c3194cc6af544da5e9
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575781"
---
# <a name="iactivescriptclose"></a>IActiveScript::Close
スクリプトエンジンが現在読み込まれているスクリプトを破棄し、その状態を失わせ、他のオブジェクトに対するインターフェイスポインターを解放して、closed 状態にします。 イベントシンク、直ちに実行されたスクリプトテキスト、および既に進行中のマクロの呼び出しは、状態が変更される前に完了します (実行中のスクリプトスレッドをキャンセルするには、 [IActiveScript:: InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)を使用します)。 循環参照の問題を防ぐために、インターフェイスが解放される前に、このメソッドを作成ホストから呼び出す必要があります。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Close(void);  
```  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|[値]|説明|  
|-----------|-------------|  
|`S_OK`|成功。|  
|`E_UNEXPECTED`|呼び出しは想定されていませんでした (たとえば、スクリプトエンジンは既に closed 状態です)。|  
|`OLESCRIPT_S_PENDING`|メソッドは正常にキューに登録されましたが、状態はまだ変更されていません。 状態が変化すると、 [IActiveScriptSite:: OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md)メソッドに対してサイトがコールバックされます。|  
|`S_FALSE`|メソッドは成功しましたが、スクリプトは既に閉じられています。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)