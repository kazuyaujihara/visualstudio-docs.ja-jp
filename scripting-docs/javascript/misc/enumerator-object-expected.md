---
title: Enumerator オブジェクトが必要です |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5015
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: dc6e32c1-a6e6-4e12-ac99-e3f65f91c8d7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 06005f635e5173e903cfba6a952750d64181d0bf
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60064870"
---
# <a name="enumerator-object-expected"></a>Enumerator オブジェクトが必要です
呼び出そうとしたか、 **Enumerator.prototype.atEnd、Enumerator.prototype.item、Enumerator.prototype.moveFirst、** または**Enumerator.prototype.moveNext**他の型のオブジェクトのメソッド`Enumerator`します。 呼び出し元のオブジェクト型でなければなりません`Enumerator`します。 この規則に違反するコードの例を次に示します。  
  
```JavaScript  
var o = new Object;  
o.f = Enumerator.prototype.atEnd;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- のみを呼び出す、 **Enumerator.prototype.atEnd**、 **Enumerator.prototype.item**、 **Enumerator.prototype.moveFirst**、または**Enumerator.prototype.moveNext**型のオブジェクトに対するメソッド`Enumerator`します。 オブジェクトかどうかを確認するを`Enumerator`オブジェクトを使用します。  
  
    ```js
    if(x instanceof Enumerator)  
    ```  
  
## <a name="see-also"></a>関連項目  
 [Enumerator オブジェクト](../../javascript/reference/enumerator-object-javascript.md)