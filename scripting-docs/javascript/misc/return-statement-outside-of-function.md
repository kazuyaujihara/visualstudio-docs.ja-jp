---
title: "'return' ステートメントが関数の外側で |Microsoft Docs"
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 03568f9f-5f4f-4a10-a738-9a73f3832b9e
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 01ef96385d5fe3dccf14a7491e67983d39913280
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63006407"
---
# <a name="return-statement-outside-of-function"></a>'return' ステートメントが関数の外にあります。
使用した、`return`コードのグローバル スコープ内のステートメント。 `return`ステートメントは、関数の本体でのみ表示する必要があります。  
  
 持つ関数を呼び出す、`()`演算子は、式です。 すべての式の値であります。`return`関数によって返される値を指定するステートメントを使用します。 一般的な形式です。  
  
```js
  
return [ expression ];  
```  
  
 ときに、`return`ステートメントを実行すると、*式*が評価され、関数の値として返されます。 式がない場合**未定義**が返されます。  
  
 関数の実行を停止するときに、`return`関数本体に残っている他のステートメントがある場合でも、ステートメントを実行します。 このルールの例外は場合、**返す**ステートメント内で発生、**お試しください**ブロックは、対応する**最後に**ブロック、コード、 **最後に**ブロックは、関数が戻る前に実行されます。  
  
 実行することがなく、関数本体の末尾に達したため、関数が返す場合、`return`ステートメントで返される値が、**未定義**値 (つまり、関数の結果より大きな式の一部として使用できません).  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 削除、 `return` (グローバル スコープ)、コードのメイン本体ステートメント。  
  
## <a name="see-also"></a>関連項目  
 [return ステートメント](../../javascript/reference/return-statement-javascript.md)   
 [関数オブジェクト](../../javascript/reference/function-object-javascript.md)   
 [caller プロパティ (Function)](../../javascript/reference/caller-property-function-javascript.md)