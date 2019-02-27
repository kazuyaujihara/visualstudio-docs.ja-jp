---
title: VBArray が必要です |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5013
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f2998d7d-13a4-4bbe-b872-3ff3316551e4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 159a5dd0195cc0cbb244664d75e19d1ac6af3dec
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "56843417"
---
# <a name="vbarray-expected"></a>VBArray が必要です。
必要ですが、Visual Basic の safeArray、されていないオブジェクトを指定しています。  
  
```js
new VBArray(safeArray);  
```  
  
 VBArrays は読み取り専用で、直接作成することはできません。 SafeArray の引数は、VBArray 値でありに渡される前に VBArray 値を取得する必要がありますが、`VBArray`コンス トラクター。 この操作は、既存の ActiveX またはその他のオブジェクトから値を取得することによってのみ行うことができます。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   のみを渡すこと**VBArray**オブジェクトを**VBArray**コンス トラクター。  
  
## <a name="see-also"></a>関連項目  
 [VBArray オブジェクト](../../javascript/reference/vbarray-object-javascript.md)   
 [配列の使用](../../javascript/advanced/using-arrays-javascript.md)