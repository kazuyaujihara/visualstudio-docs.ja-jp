---
title: 条件付きコンパイルは無効になります |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 59a030b0-a6c6-47f2-b90e-c0ed204d5116
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8317121b840d82ab12d4a9e1ca50f6680eb1e21d
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60051740"
---
# <a name="conditional-compilation-is-turned-off"></a>条件付きコンパイルは無効になっています。
初めてオンにする条件付きコンパイルなしの条件付きコンパイル変数を使用しようとしました。 通知の条件付きコンパイルの有効化、[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]コンパイラに条件付きコンパイル変数としてで始まる識別子。 条件付きステートメントを使用してコードを開始することで行います。  
  
```js
/*@cc_on @*/  
```  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 条件付きコードの先頭に次のステートメントを追加します。  
  
    ```JavaScript  
    /*@cc_on @*/  
    ```  
  
## <a name="see-also"></a>関連項目  
 [条件付きコンパイル](../../javascript/advanced/conditional-compilation-javascript.md)   
 [条件付きコンパイル変数](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@cc_on ステートメント](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@if ステートメント](../../javascript/reference/at-if-statement-javascript.md)   
 [@set ステートメント](../../javascript/reference/at-set-statement-javascript.md)