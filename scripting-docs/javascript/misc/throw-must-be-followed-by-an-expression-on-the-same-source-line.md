---
title: 同じソース行の式で throw を後に |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1035
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b03b7747-01a1-40c6-af80-a1dd70bc5781
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5d2989b2ebb5cf0095736d5667f85a807558c495
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "56841144"
---
# <a name="throw-must-be-followed-by-an-expression-on-the-same-source-line"></a>Throw ステートメントに指定する式は、ソース コードの同一行に記述してください
使用した、`throw`キーワードが従っていなかった、式が同じソース行にします。 A`throw`ステートメントは、2 つの部分で構成されています。`throw`キーワードの後に、式がスローされます。 例:  
  
```JavaScript  
if (denominator == 0) {  
 throw new DivideByZeroException();  
}  
```  
  
 これら 2 つのコンポーネントを分割することはできません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   必ず、`throw`キーワードとがスローされる式が同じ行に表示されます。  
  
## <a name="see-also"></a>関連項目  
 [Error オブジェクト](../../javascript/reference/error-object-javascript.md)   
 [Throw ステートメント](../../javascript/reference/throw-statement-javascript.md)   
 [try… catch… finally ステートメント](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)