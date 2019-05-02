---
title: 関数の結果に割り当てることはできません |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5003
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ee8ffb3a-1451-4cb3-99bf-5e9cf8b77d79
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 226056f139e45f432d757aff8f8774b013742de3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946603"
---
# <a name="cannot-assign-to-a-function-result"></a>関数の結果に割り当てられません。
関数の結果に値を代入しようとしました。 関数の結果を変数に割り当てることができますが、変数として使用できません。 関数自体に新しい値を代入する場合は、(関数呼び出し演算子) のかっこを省略します。 次の例では、このエラーを生成するような状況を示します。  
  
```js
myFunction() = 42;  // Attempting to assign the value 42 to the result of the function call.  
```  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- ものとして関数呼び出しの結果の値を使用しないで*に割り当てる*します。 関数呼び出しの結果を割り当てることができます*変数に*場合。  
  
    ```JavaScript  
    myVar = myFunction(42);  
    ```  
  
- 代わりに、割り当てることができます、関数自体 (および戻り値ではありません) を変数にします。  
  
    ```JavaScript  
    myFunction = new Function("return 42;");  
    ```  
  
## <a name="see-also"></a>関連項目  
 [関数オブジェクト](../../javascript/reference/function-object-javascript.md)   
 [JavaScript コードの記述](../../javascript/writing-javascript-code.md)   
 [関数](../../javascript/functions-javascript.md)