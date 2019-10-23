---
title: 配列の長さは、有限の正の整数でなければなりません |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5029
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1a467040-4702-4178-848f-418a5974e907
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 69494f1485a97ff4f2c98cf2493e5d0bc5b8aa9f
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576080"
---
# <a name="array-length-must-be-a-finite-positive-integer"></a>配列の長さは、有限の正の整数でなければなりません。
整数ではない引数を使用して、**配列**コンストラクターを呼び出しています (0 と正の整数のセットで構成される整数)。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 新しい `Array` オブジェクトを作成する場合にのみ、正の整数を使用します。 整数ではない1つの要素を持つ配列を作成する場合は、2段階のプロセスで実行します。 まず、1つの要素を持つ配列を作成してから、最初の要素 (array [0]) に値を配置します。 このエラーを生成する例を次に示します。  
  
    ```JavaScript  
    var piArray = new Array(3.14159);  
    ```  
  
     次の例は、単一の数値要素を持つ配列を指定する正しい方法を示しています。  
  
    ```JavaScript  
    var piArray = new Array(1);  
    piArray [0] = 3.14159;  
    ```  
  
     配列のサイズの上限は、最大の整数値 (約 40億) を超えています。  
  
## <a name="see-also"></a>関連項目  
 [配列の使用](../../javascript/advanced/using-arrays-javascript.md)