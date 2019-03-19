---
title: SCRIPTTRACEINFO 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: cb8a4767-8c8e-4fa0-a735-038767a8c500
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ed2c6566db8209280be7f102a55c7de8cf85c44
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58155811"
---
# <a name="scripttraceinfo-enumeration"></a>SCRIPTTRACEINFO 列挙型
トレースしているスクリプト イベントを表します。 使用される、 [iactivescriptsitetraceinfo::sendscripttraceinfo メソッド](../../winscript/reference/iactivescriptsitetraceinfo-sendscripttraceinfo-method.md)します。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef enum tagSCRIPTTRACEINFO {      SCRIPTTRACEINFO_SCRIPTSTART = 0,      SCRIPTTRACEINFO_SCRIPTEND   = 1,      SCRIPTTRACEINFO_COMCALLSTART    = 2,      SCRIPTTRACEINFO_COMCALLEND  = 3,      SCRIPTTRACEINFO_CREATEOBJSTART  = 4,      SCRIPTTRACEINFO_CREATEOBJEND    = 5,      SCRIPTTRACEINFO_GETOBJSTART = 6,      SCRIPTTRACEINFO_GETOBJEND   = 7,  } SCRIPTTRACEINFO ;  
```  
  
## <a name="enumeration-values"></a>列挙値  
  
|||  
|-|-|  
|SCRIPTTRACEINFO_SCRIPTSTART|スクリプトの開始。|  
|SCRIPTTRACEINFO_SCRIPTEND|スクリプトの最後。|  
|SCRIPTTRACEINFO_COMCALLSTART|COM の呼び出しの開始。|  
|SCRIPTTRACEINFO_COMCALLEND|COM の呼び出しの終了。|  
|SCRIPTTRACEINFO_CREATEOBJSTART|オブジェクトの作成の開始。|  
|SCRIPTTRACEINFO_CREATEOBJEND|オブジェクトの作成の終了。|  
|SCRIPTTRACEINFO_GETOBJSTART|GetObject の呼び出しの開始。|  
|SCRIPTTRACEINFO_GETOBJEND|GetObject の呼び出しの終了。|