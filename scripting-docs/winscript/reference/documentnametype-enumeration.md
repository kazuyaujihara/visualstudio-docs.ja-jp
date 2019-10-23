---
title: DOCUMENTDOCUMENTENUMERATION |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DOCUMENTNAMETYPE
apilocation:
- scrobj.dll
helpviewer_keywords:
- DOCUMENTNAMETYPE enumeration
ms.assetid: d36d550e-efb4-493d-8971-4de267005654
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 401eb759523ed1a33d24c3a298db0b3de2b7d5a7
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575875"
---
# <a name="documentnametype-enumeration"></a>DOCUMENTNAMETYPE 列挙型
ドキュメント用に取得する型を記述します。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef enum tagDOCUMENTNAMETYPE {  
   DOCUMENTNAMETYPE_APPNODE,  
   DOCUMENTNAMETYPE_TITLE,  
   DOCUMENTNAMETYPE_FILE_TAIL,  
   DOCUMENTNAMETYPE_URL,  
DOCUMENTNAMETYPE_UNIQUE_TITLE,} DOCUMENTNAMETYPE;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|DOCUMENTNAMETYPE_APPNODE|アプリケーションツリーに表示される名前を取得します。|  
|DOCUMENTNAMETYPE_TITLE|ビューアーのタイトルバーに表示される名前を取得します。|  
|DOCUMENTNAMETYPE_FILE_TAIL|パスを含まないファイル名を取得します。|  
|DOCUMENTNAMETYPE_URL|ドキュメントの URL を取得します。|  
|DOCUMENTNAMETYPE_UNIQUE_TITLE|識別用の列挙を追加したタイトルを取得します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト デバッガーの定数、列挙型、および構造体](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)