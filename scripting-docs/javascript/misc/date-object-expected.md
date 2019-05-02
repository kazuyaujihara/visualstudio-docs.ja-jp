---
title: Date オブジェクトが必要です。 |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5006
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d6ab82e6-ca64-46b4-a06c-5c6b0aa057cb
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2767ffc16b637c6b1e7bdf51cb0815d71f58edac
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946382"
---
# <a name="date-object-expected"></a>Date オブジェクトが必要です。
呼び出そうとしたか、 **Date.prototype.toString**または**Date.prototype.valueOf**メソッド以外の型のオブジェクトを`Date`します。 呼び出し元のオブジェクト型でなければなりません`Date`します。 例えば:  
  
```JavaScript  
var o = new Object;  
o.f = Date.prototype.toString;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- のみを呼び出す、 **Date.prototype.toString**または**Date.prototype.valueOf**型のオブジェクトに対するメソッド`Date`します。  
  
## <a name="see-also"></a>関連項目  
 [Date オブジェクト](../../javascript/reference/date-object-javascript.md)   
 [getDate メソッド (Date)](../../javascript/reference/getdate-method-date-javascript.md)   
 [組み込みオブジェクト](../../javascript/intrinsic-objects-javascript.md)