---
title: "'Catch' が必要です |Microsoft Docs"
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1033
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f1cd947f-eba2-411e-8e84-8ca86f608643
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 941d49a530b14e2af64ddcb599dd775feb347de0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62935400"
---
# <a name="expected-catch"></a>catch が必要です。
例外処理を使用した**try**ブロックしますが、関連付けられているによって記述されていない**catch**ステートメント。 例外処理メカニズムでは、例外が発生する場合に実行する必要がありますコードと共に、エラーがコード内でラップしている必要があります、**try**ブロックします。 内から例外がスローされた、**try**ブロックを使用して、**throw**ステートメントでは、外部キャッチし、**try** つまたは複数のブロックを**catch**ステートメント。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 関連付けられている追加**catch**ブロックします。  
  
- 使用してください、**finally**ブロックの代わりに、**catch**ブロックします。  
  
## <a name="see-also"></a>関連項目  
 [try… catch… finally ステートメント](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)   
 [Error オブジェクト](../../javascript/reference/error-object-javascript.md)