---
title: 関数には有効なプロトタイプ オブジェクトがありません |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5023
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b9e34652-190f-4b57-b253-df2e8c4d09c6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 413f73a53a6d4f698219139a87c449be4c155831
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60038680"
---
# <a name="function-does-not-have-a-valid-prototype-object"></a>関数には、有効なプロトタイプ オブジェクトが存在しません。
使用しようとする**instanceof**オブジェクトは、特定の関数クラスから派生しましたが、オブジェクトの再定義するかどうかを判断する`prototype`プロパティをいずれかとして`null`、または外部のオブジェクトの種類 (両方無効[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]オブジェクト)。 外部オブジェクトには、ホスト オブジェクト モデル (たとえば、Internet Explorer のドキュメントまたはウィンドウ オブジェクト) からオブジェクトまたは外部の COM オブジェクトを指定できます。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 関数のことを確認`prototype`プロパティは、有効な参照[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [関数オブジェクト](../../javascript/reference/function-object-javascript.md)   
 [prototype プロパティ (Object)](../../javascript/reference/prototype-property-object-javascript.md)