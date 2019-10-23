---
title: "' Catch ' | が必要です。Microsoft Docs"
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
ms.openlocfilehash: 8cad981e4ba469f67645aca601e6b58c18e1fab6
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573429"
---
# <a name="expected-catch"></a>catch が必要です。
例外処理**try**ブロックを使用しましたが、関連付けられた**catch**ステートメントが書き込まれませんでした。 例外処理機構では、例外が発生した場合に実行してはならないコードと共に、失敗する可能性のあるコードが**try**ブロック内にラップされている必要があります。 例外は、 **throw**ステートメントを使用して**try**ブロック内からスローされ、 **try**ブロックの外側で1つ以上の**catch**ステートメントを使用してキャッチされます。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 関連付けられた**catch**ブロックを追加します。  
  
- **Catch**ブロックの代わりに**finally**ブロックを使用してください。  
  
## <a name="see-also"></a>関連項目  
 [お試しください...キャッチ...finally ステートメント](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)の    
 [Error オブジェクト](../../javascript/reference/error-object-javascript.md)
