---
title: 'IActiveScriptGarbageCollector:: CollectGarbage |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 75f77c49-2190-4d49-a3e0-9dcf847c502b
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0539ed2cb3540cf33ceaaa15827c3ca08c156698
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573581"
---
# <a name="iactivescriptgarbagecollectorcollectgarbage"></a>IActiveScriptGarbageCollector::CollectGarbage
アクティブスクリプトホストは、このメソッドを呼び出してガベージコレクションを開始します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CollectGarbage(        SCRIPTGCTYPE scriptgctype    );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `scriptgctype`  
 から通常または完全なガベージコレクションを実行するかどうかを指定する[SCRIPTGCTYPE 列挙体](../../winscript/reference/scriptgctype-enumeration.md)。  
  
## <a name="return-value"></a>戻り値  
 HRESULT を返します。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptGarbageCollector Interface](../../winscript/reference/iactivescriptgarbagecollector-interface.md)