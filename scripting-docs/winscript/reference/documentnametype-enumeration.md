---
title: DOCUMENTNAMETYPE 列挙型 |Microsoft Docs
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
ms.openlocfilehash: 5ee258602c47951f4731dc1378542cc83d57d72b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955216"
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
|DOCUMENTNAMETYPE_APPNODE|アプリケーションのツリーに表示される名前を取得します。|  
|DOCUMENTNAMETYPE_TITLE|ビューアーのタイトル バーに表示される名前を取得します。|  
|DOCUMENTNAMETYPE_FILE_TAIL|パスを持たないファイル名を取得します。|  
|DOCUMENTNAMETYPE_URL|ドキュメントの URL を取得します。|  
|DOCUMENTNAMETYPE_UNIQUE_TITLE|Id の列挙型が付加されますタイトルを取得します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト デバッガーの定数、列挙型、および構造体](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)