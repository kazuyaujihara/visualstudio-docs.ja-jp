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
ms.openlocfilehash: e1e34be9f8eab5171af0e2553d5777b0958bf3c2
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840871"
---
# <a name="exception-thrown-and-not-caught"></a>例外がスローされ、キャッチされませんでした。
含まれていること、`throw`内では、コード内のステートメントが囲まれていない、**お試しください**ブロック、または関連付けられていませんが**キャッチ**エラーをトラップするブロック。 内から例外がスローされた、**を再試行してください**ブロックを使用して、**スロー**ステートメントでは、外キャッチし、**お試しください**でブロック、**キャッチ**ステートメント。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   例外をスローするコードを囲む、**お試しください**がありますが、対応することを確認して、ブロック**キャッチ**ブロックします。  
  
-   Catch ステートメントを例外の正しい形式の想定を確認します。  
  
-   場合は、例外を再スローすると、別の対応する catch ステートメントがあることを確認します。  
  
## <a name="see-also"></a>関連項目  
 [Error オブジェクト](../../javascript/reference/error-object-javascript.md)   
 [Throw ステートメント](../../javascript/reference/throw-statement-javascript.md)   
 [try… catch… finally ステートメント](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)