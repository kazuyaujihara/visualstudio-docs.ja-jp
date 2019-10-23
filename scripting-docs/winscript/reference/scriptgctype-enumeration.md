---
title: SCRIPTGCTYPE 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: f289cc7d-2a69-4720-bee0-ea27d054f308
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7fce16c756cf06c8cf01937114402832570a0cd3
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574388"
---
# <a name="scriptgctype-enumeration"></a>SCRIPTGCTYPE 列挙型
実行するガベージコレクションの型。 [IActiveScriptGarbageCollector:: CollectGarbage](../../winscript/reference/iactivescriptgarbagecollector-collectgarbage.md)メソッドで使用されます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
typedef enum tagSCRIPTGCTYPE {    SCRIPTGCTYPE_NORMAL           = 0,    SCRIPTGCTYPE_EXHAUSTIVE       = 1,} SCRIPTGCTYPE;  
```  
  
## <a name="enumeration-values"></a>列挙値  
  
|||  
|-|-|  
|SCRIPTGCTYPE_NORMAL|通常のガベージコレクションを実行します。 整数値は0です。|  
|SCRIPTGCTYPE_EXHAUSTIVE|完全なガベージコレクションを実行します。 整数値は1です。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプトの定数、列挙型、およびエラー コード](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)