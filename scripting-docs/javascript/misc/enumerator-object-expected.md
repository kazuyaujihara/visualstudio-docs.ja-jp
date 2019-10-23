---
title: Enumerator オブジェクトが必要です。Microsoft Docs
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
ms.openlocfilehash: d90b6b923f631c7785428a1b3879528e97c1bfd6
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572866"
---
# <a name="enumerator-object-expected"></a>列挙子オブジェクトが必要です。
@No__t_2 以外の型のオブジェクトに対して、 **enumerator** 、enumerator、列挙子、列挙子、列挙子、または**列挙**子を呼び出そうとしています。 この種類の呼び出しのオブジェクトは `Enumerator` 型である必要があります。 この規則を解除するコードの例を次に示します。  
  
```JavaScript  
var o = new Object;  
o.f = Enumerator.prototype.atEnd;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- @No__t_4 型のオブジェクトに対して **、enumerator、** enumerator **、enumerator、** **enumerator、enumerator**、または enumerator. prototype. **moveNext**を呼び出します。 オブジェクトが `Enumerator` オブジェクトであるかどうかを調べるには、次のように使用します。  
  
    ```js
    if(x instanceof Enumerator)  
    ```  
  
## <a name="see-also"></a>関連項目  
 [Enumerator オブジェクト](../../javascript/reference/enumerator-object-javascript.md)