---
title: SCRIPT_DEBUGGER_OPTIONS 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SCRIPT_DEBUGGER_OPTIONS Enumeration
ms.assetid: aef41ec0-6f65-48e8-a69e-44b4e4fb929f
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c69d419732786442cda275bf85c74ab2b9d3e870
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574558"
---
# <a name="script_debugger_options-enumeration"></a>SCRIPT_DEBUGGER_OPTIONS 列挙型
アタッチされたデバッガーに適用される一連のオプションと機能を示します。 [IDebugApplicationNode100:: GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md)と[IDebugApplicationNode100:: SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)で使用されます。  
  
> [!IMPORTANT]
> これらの定数は、PDM v1.1 以上で実装されています。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef SCRIPT_DEBUGGER_OPTIONS  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|[値]|説明|  
|------------|-----------|-----------------|  
|SDO_NONE|0x00000000|オプションが設定されていません。|  
|SDO_ENABLE_FIRST_CHANCE_EXCEPTIONS|0x00000001|例外がスローされたときに、スクリプトランタイムが BREAKREASON_ERROR イベントを発生させることを示します。 このオプションは、デバッガーで設定することも、`Debug.enableFirstChanceExceptions(<true&#124;false>)` を使用してユーザーコードで設定することもできます。|  
|SDO_ENABLE_WEB_WORKER_SUPPORT|0x00000002|アタッチされたデバッガーが web ワーカーをサポートしていることを示します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト デバッガーの定数、列挙型、および構造体](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)