---
title: サポートされていない値の引数の循環参照 |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5034
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 5d06f0fa-86f5-49d1-8d50-af1759990f43
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a31b56b4b2d568b3bc3fd59f876f5052b9f6faff
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946369"
---
# <a name="circular-reference-in-value-argument-not-supported"></a>value 引数の循環参照はサポートされません。
呼び出しが試行された`JSON.stringify`値が無効です。 `value`引数、配列またはオブジェクトを循環参照が含まれています。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 引数の循環参照を削除します。  
  
## <a name="example"></a>例  
 に、この例では、コードによってランタイム エラーが発生`john`への参照を持つ`mary`と`mary`への参照を持つ`john`します。 循環参照を削除するか、削除または未設定プロパティ`brother`から、`mary`オブジェクトまたは`sister`プロパティから、`john`オブジェクト。  
  
```JavaScript  
var john = new Object();  
var mary = new Object();  
john.sister = mary;  
mary.brother = john;  
  
// This line causes a runtime error.  
var error = JSON.stringify(john);  
```  
  
## <a name="see-also"></a>関連項目  
 [JSON オブジェクト](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse 関数](../../javascript/reference/json-parse-function-javascript.md)   
 [JavaScript ランタイム エラー](../../javascript/reference/javascript-run-time-errors.md)