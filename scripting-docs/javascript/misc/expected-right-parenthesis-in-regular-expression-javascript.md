---
title: 予想 ')' では、正規表現 (JavaScript) |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5020
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 2087ba1d-9783-4d40-b609-e8542f579f7f
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 72b4cf24b4b738b7ca71e364d7be6486313a4844
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840806"
---
# <a name="expected--in-regular-expression-javascript"></a>正規表現の中に ')' が必要です (JavaScript)
正規表現キャプチャ、アサーション、またはグループを作成しようとしましたが、終わりかっこが含まれていません。 かっこでは、正規表現でいくつかの目的があります。 主に、アサーション、またはパターンをグループ化によって 1 つの単位として、アイテムを処理できるようにする、サブ式のキャプチャに使用されます *、+、? などです。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   右端の閉じかっこを追加します。  
  
    > [!NOTE]
    >  1 つのかっこと一致する場合は、円記号のエスケープ\\(によって特殊文字として解釈されないように -[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]します。  
  
## <a name="see-also"></a>関連項目  
 [Regular Expression オブジェクト](../../javascript/reference/regular-expression-object-javascript.md)   
 [正規表現構文 (JavaScript)](https://msdn.microsoft.com/library/1400241x)