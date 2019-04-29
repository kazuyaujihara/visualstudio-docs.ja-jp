---
title: ループの外 'break' を含めることはできません |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1019
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 11d02172-2a78-4705-a730-d21111db5f42
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a02848230187eb465d56ed73e44380e4b043b117
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946629"
---
# <a name="cant-have-break-outside-of-loop"></a>'break' をループの外に設定できません。
使用しようとする、 **break**ループ外にあるキーワード。 **Break**キーワードを使用して、ループの終了をまたは`switch`ステートメント。 ループの本体に埋め込む必要があります、または`switch`ステートメント。 ただし、**ラベル**break キーワードをフォローできます。  
  
```js
break labelname;  
```  
  
 ラベル付きののみ必要があります、 **break**入れ子になったループを使用しているときに、キーワードまたは`switch`ステートメントと最も内側のものではないループから抜け出す必要。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 確認、 **break**外側のループまたは switch ステートメント内でキーワードが表示されます。  
  
## <a name="see-also"></a>関連項目  
 [break ステートメント](../../javascript/reference/break-statement-javascript.md)   
 [プログラム フローの制御](../../javascript/controlling-program-flow-javascript.md)   
 [スクリプトのトラブルシューティング](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)