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
ms.openlocfilehash: a5112f52e9d48417cfd63a514d22a034168c1aea
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58152117"
---
# <a name="applicationnodeeventfilter-enumeration"></a>APPLICATION_NODE_EVENT_FILTER 列挙型
コードのドキュメントをフィルター処理するときに除外するノードの種類を指定します。 使用される[IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md)と[IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)  
  
> [!IMPORTANT]
>  これらの定数は、PDM v10.0 によって以降に実装されます。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
typedef enum tagAPPLICATION_NODE_EVENT_FILTER {    FILTER_EXCLUDE_NOTHING = 0,    FILTER_EXCLUDE_ANONYMOUS_CODE = 0x1,    FILTER_EXCLUDE_EVAL_CODE = 0x2} APPLICATION_NODE_EVENT_FILTER;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|[値]|説明|  
|------------|-----------|-----------------|  
|FILTER_EXCLUDE_NOTHING|0x00000000|すべてのイベントを送信します。|  
|FILTER_EXCLUDE_ANONYMOUS_CODE|0x00000001|匿名のコードのノードを除外します。 これらのノードがの JScript ランタイムによって使用される`new Function([args,] <code>)'`します。|  
|FILTER_EXCLUDE_EVAL_CODE|0x00000002|Eval コード ノードを除外します。 これらのノードは、eval サポートの JScript ランタイムによって使用されます。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト デバッガーの定数、列挙型、および構造体](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)