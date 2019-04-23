---
title: 関数が必要です |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5002
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f62ade94-9f6f-4832-9b9b-49a06a385bbe
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4442143b2766ed3608a852d0f811a6b943fd19df
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60117055"
---
# <a name="function-expected"></a>関数が必要です。
いずれかを呼び出すしようとするか、**関数プロトタイプ**できなかったオブジェクトのメソッドを`Function`オブジェクト、またはするには、関数呼び出しのコンテキストでオブジェクトを使用します。 次のコードがこのエラーを生成するため、たとえば、**例**関数ではありません。  
  
```JavaScript  
var example = new Object();  // Create a new object called "example".  
var x = example();           // Try and call example as if it were a function.  
```  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- のみを呼び出す**関数プロトタイプ**メソッド`Function`オブジェクト。  
  
- 関数呼び出し演算子を使用することを確認します。`()`関数のみを呼び出します。  
  
## <a name="see-also"></a>関連項目  
 [関数オブジェクト](../../javascript/reference/function-object-javascript.md)   
 [prototype プロパティ (Object)](../../javascript/reference/prototype-property-object-javascript.md)