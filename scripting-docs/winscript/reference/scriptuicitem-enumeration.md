---
title: SCRIPTUICITEM 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: fbf01f1b-5d7f-4d92-8d10-3da65e352d93
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bd454780b4360daf844697ad92ab8a4e9da29317
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62840136"
---
# <a name="scriptuicitem-enumeration"></a>SCRIPTUICITEM 列挙型
UI 項目の種類を表します。 使用される、 [iactivescriptsiteuicontrol::getuibehavior メソッド](../../winscript/reference/iactivescriptsiteuicontrol-getuibehavior-method.md)します。  
  
## <a name="syntax"></a>構文  
  
```vb  
typedef enum tagSCRIPTUICITEM {     SCRIPTUICITEM_INPUTBOX = 1,     SCRIPTUICITEM_MSGBOX = 2,     } SCRIPTUICITEM;   
```  
  
## <a name="enumeration-values"></a>列挙値  
  
|||  
|-|-|  
|SCRIPTUICITEM_INPUTBOX|入力コントロール。|  
|SCRIPTUICITEM_MSGBOX|メッセージ ボックスです。|