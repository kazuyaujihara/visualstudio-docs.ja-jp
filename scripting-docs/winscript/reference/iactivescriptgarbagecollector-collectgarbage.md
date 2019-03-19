---
title: IActiveScriptGarbageCollector::CollectGarbage |Microsoft Docs
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
ms.openlocfilehash: db8683534e449b2cdd8fcdb344c245d93da8fafc
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144668"
---
# <a name="iactivescriptgarbagecollectorcollectgarbage"></a>IActiveScriptGarbageCollector::CollectGarbage
アクティブ スクリプト ホストは、ガベージ コレクションを開始するには、このメソッドを呼び出します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CollectGarbage(        SCRIPTGCTYPE scriptgctype    );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `scriptgctype`  
 [in][SCRIPTGCTYPE 列挙型](../../winscript/reference/scriptgctype-enumeration.md)通常または完全なガベージ コレクションを実行するかどうかを指定します。  
  
## <a name="return-value"></a>戻り値  
 HRESULT を返します。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptGarbageCollector Interface](../../winscript/reference/iactivescriptgarbagecollector-interface.md)