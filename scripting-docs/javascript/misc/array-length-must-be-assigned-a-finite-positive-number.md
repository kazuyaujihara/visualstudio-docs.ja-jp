---
title: 配列の長さに有限の正数を割り当てる必要があります |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: c51c66a4-a543-4e95-b18d-2cfbcb3d1fdd
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 39f2720efbcd8defffb9d0c77047a50e57939e95
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60082348"
---
# <a name="array-length-must-be-assigned-a-finite-positive-number"></a>配列の長さは、割り当てられた有限の正数でなければなりません。
設定するときに、**長さ**、既存のプロパティ**配列**オブジェクト、配列の長さが正の整数または 0 を指定します。 このエラーは、値を割り当てるときに発生します。、**長さ**のプロパティ、`Array`が負の値をオブジェクトまたは非数 (`NaN`)。 なお[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]に自動的に小数部を整数に変換します。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- Length プロパティに正の整数を割り当てます。 最大の整数値 (約 40億) 以外の値、配列のサイズの上限はありません。 次の例では、設定するには、**長さ**のプロパティ、**配列**オブジェクト。  
  
    ```JavaScript  
    var my_array = new Array();  
    my_array.length = 99;  
    ```  
  
## <a name="see-also"></a>関連項目  
 [配列の使用](../../javascript/advanced/using-arrays-javascript.md)