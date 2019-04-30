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
ms.openlocfilehash: 7daf5d876f68168ce0b58ea2cc9b52a309107bc6
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446532"
---
# <a name="expected--in-regular-expression-javascript"></a>正規表現の中に ')' が必要です (JavaScript)
正規表現キャプチャ、アサーション、またはグループを作成しようとしましたが、終わりかっこが含まれていません。 かっこでは、正規表現でいくつかの目的があります。 主に、アサーション、またはパターンをグループ化によって 1 つの単位として、アイテムを処理できるようにする、サブ式のキャプチャに使用されます *、+、? などです。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 右端の閉じかっこを追加します。  
  
    > [!NOTE]
    > 1 つのかっこと一致する場合は、円記号のエスケープ\\(によって特殊文字として解釈されないように -[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]します。  
  
## <a name="see-also"></a>関連項目  
 [Regular Expression オブジェクト](../../javascript/reference/regular-expression-object-javascript.md)   
 [正規表現構文 (JavaScript)](https://msdn.microsoft.com/library/1400241x)