---
title: APPLICATION_NODE_EVENT_FILTER 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- APPLICATION_NODE_EVENT_FILTER Constants
ms.assetid: dccb2cf7-0598-46f8-b3eb-16b752815e96
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 481e015ec84d833f52220276bffa4ce0163f98ff
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572649"
---
# <a name="application_node_event_filter-enumeration"></a>APPLICATION_NODE_EVENT_FILTER 列挙型
コードドキュメントをフィルター処理するときに除外するノードの種類を指定します。 [IDebugApplicationNode100:: GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md)と[IDebugApplicationNode100:: SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)で使用されます。  
  
> [!IMPORTANT]
> これらの定数は、PDM v1.1 以上で実装されています。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
typedef enum tagAPPLICATION_NODE_EVENT_FILTER {    FILTER_EXCLUDE_NOTHING = 0,    FILTER_EXCLUDE_ANONYMOUS_CODE = 0x1,    FILTER_EXCLUDE_EVAL_CODE = 0x2} APPLICATION_NODE_EVENT_FILTER;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|[値]|説明|  
|------------|-----------|-----------------|  
|FILTER_EXCLUDE_NOTHING|0x00000000|すべてのイベントを送信します。|  
|FILTER_EXCLUDE_ANONYMOUS_CODE|0x00000001|匿名コードノードを除外します。 これらのノードは、JScript ランタイムによって `new Function([args,] <code>)'` に使用されます。|  
|FILTER_EXCLUDE_EVAL_CODE|0x00000002|Eval コードノードを除外します。 これらのノードは、JScript ランタイムで eval サポートに使用されます。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト デバッガーの定数、列挙型、および構造体](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)