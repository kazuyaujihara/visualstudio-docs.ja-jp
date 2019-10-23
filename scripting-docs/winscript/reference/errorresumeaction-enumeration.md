---
title: ERRORRESUMEACTION 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ERRORRESUMEACTION
apilocation:
- scrobj.dll
helpviewer_keywords:
- ERRORRESUMEACTION enumeration
ms.assetid: a68293c8-056b-439f-83e7-69e4a38f4976
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ad9b8598cb027c96f6fb6fad6f3d343e6058cfdb
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575857"
---
# <a name="errorresumeaction-enumeration"></a>ERRORRESUMEACTION 列挙型
ランタイム エラーから継続する方法について記述します。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef enum tagERRORRESUMEACTION {  
   ERRORRESUMEACTION_ReexecuteErrorStatement,  
   ERRORRESUMEACTION_AbortCallAndReturnErrorToCaller,  
   ERRORRESUMEACTION_SkipErrorStatement,  
} ERRORRESUMEACTION;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|ERRORRESUMEACTION_ReexecuteErrorStatement|エラーを生成したステートメントを再実行します。|  
|ERRORRESUMEACTION_AbortCallAndReturnErrorToCaller|言語エンジンがエラーを処理できるようにします。|  
|ERRORRESUMEACTION_SkipErrorStatement|エラーを生成したステートメントの後のコードで実行を再開します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト デバッガーの定数、列挙型、および構造体](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)