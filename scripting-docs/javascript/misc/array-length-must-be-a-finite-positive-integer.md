---
title: 配列の長さは、有限の正の整数を指定する必要があります |Microsoft Docs
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
ms.openlocfilehash: 31673205a7ca94783985e0249c5664b4bbca6147
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62818125"
---
# <a name="array-length-must-be-a-finite-positive-integer"></a>配列の長さは、有限の正の整数でなければなりません。
呼び出している、**配列**(0 と正の整数のセットの値は整数で構成されます) の整数でない引数を持つコンス トラクター。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 正の整数を使用して、新しいを作成する場合にのみ`Array`オブジェクト。 整数でない 1 つの要素の配列を作成する場合は、2 段階のプロセスで行うこと。 1 つの要素を持つ配列を作成し、(array[0]) の最初の要素に値を配置します。 このエラーを生成する例を次に示します。  
  
    ```JavaScript  
    var piArray = new Array(3.14159);  
    ```  
  
     次の例では、1 つの数値要素の配列を指定する正しい方法を示します。  
  
    ```JavaScript  
    var piArray = new Array(1);  
    piArray [0] = 3.14159;  
    ```  
  
     最大の整数値 (約 40億) 以外の値、配列のサイズの上限はありません。  
  
## <a name="see-also"></a>関連項目  
 [配列の使用](../../javascript/advanced/using-arrays-javascript.md)