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
ms.openlocfilehash: 906a309b25a1fe606fb37f8cbab70040e5a4c46f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62840188"
---
# <a name="scriptthreadstate-enumeration"></a>SCRIPTTHREADSTATE 列挙型
スクリプト エンジンでは、スレッドの状態を指定します。 この列挙体を使って、 [IActiveScript::GetScriptThreadState](../../winscript/reference/iactivescript-getscriptthreadstate.md)メソッド。  
  
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
|SCRIPTTHREADSTATE_NOTINSCRIPT|指定されたスレッドはされていない処理がすぐに実行されるスクリプトのテキストをスクリプト化されたイベントを処理または、スクリプト マクロを実行します。|  
|SCRIPTTHREADSTATE_RUNNING|指定されたスレッドはアクティブに処理がすぐに実行されるスクリプトのテキストをスクリプト化されたイベントを処理か、スクリプトのマクロを実行します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプトの定数、列挙型、およびエラー コード](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)