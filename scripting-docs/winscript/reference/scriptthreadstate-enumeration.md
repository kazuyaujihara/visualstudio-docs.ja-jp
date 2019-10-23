---
title: SCRIPTTHREADSTATE 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- SCRIPTTHREADSTATE
apilocation:
- scrobj.dll
helpviewer_keywords:
- SCRIPTTHREADSTATE enum
ms.assetid: 975ec66b-c095-40ac-8ba9-631adb97b589
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bc4ef840310c27ccbadce2ed4f632514b555ef98
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575657"
---
# <a name="scriptthreadstate-enumeration"></a>SCRIPTTHREADSTATE 列挙型
スクリプトエンジンのスレッドの状態を指定します。 この列挙体は、 [IActiveScript:: GetScriptThreadState](../../winscript/reference/iactivescript-getscriptthreadstate.md)メソッドによって使用されます。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef enum tagSCRIPTTHREADSTATE {  
    SCRIPTTHREADSTATE_NOTINSCRIPT  = 0,  
    SCRIPTTHREADSTATE_RUNNING      = 1  
} SCRIPTTHREADSTATE;  
```  
  
## <a name="enumeration-values"></a>列挙値  
  
|||  
|-|-|  
|SCRIPTTHREADSTATE_NOTINSCRIPT|指定されたスレッドは、現在スクリプト化されたイベントを処理していないか、直ちに実行されたスクリプトテキストを処理しています。|  
|SCRIPTTHREADSTATE_RUNNING|指定されたスレッドは、スクリプト化されたイベントのアクティブな処理、すぐに実行されたスクリプトテキストの処理、またはスクリプトマクロの実行を行います。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプトの定数、列挙型、およびエラー コード](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)