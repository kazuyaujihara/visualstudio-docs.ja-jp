---
title: 例外がスローされキャッチされない |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5022
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b5235490-a8e7-42e3-804e-d85235bc6f05
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bae4ed0a335a9c12d16cb46208f77c4b66f12547
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946330"
---
# <a name="exception-thrown-and-not-caught"></a>例外がスローされ、キャッチされませんでした。
含まれていること、`throw`内では、コード内のステートメントが囲まれていない、**try** ブロック、または関連付けられていませんが**catch** エラーをトラップするブロック。 内から例外がスローされた、**try** ブロックを使用して、**throw** ステートメントでは、外キャッチし、**try**でブロック、**catch** ステートメント。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 例外をスローするコードを囲む、**try**がありますが、対応することを確認して、ブロック**catch** ブロックします。  
  
- Catch ステートメントを例外の正しい形式の想定を確認します。  
  
- 場合は、例外を再スローすると、別の対応する catch ステートメントがあることを確認します。  
  
## <a name="see-also"></a>関連項目  
 [Error オブジェクト](../../javascript/reference/error-object-javascript.md)   
 [Throw ステートメント](../../javascript/reference/throw-statement-javascript.md)   
 [try… catch… finally ステートメント](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)