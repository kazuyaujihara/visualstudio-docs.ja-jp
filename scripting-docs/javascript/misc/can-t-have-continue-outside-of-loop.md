---
title: ループの外 'の continue' を含めることはできません |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1020
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d2d95259-b2bc-4069-9876-60c30ad600a3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 804c23c45379a10d91c2888ac321c18f2067a1e4
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67825689"
---
# <a name="cant-have-continue-outside-of-loop"></a>'continue' をループの外に設定できません。
ループ外で **continue** ステートメントを使用しようとしました。 **continue** ステートメントは、以下の本文内でのみ使用できます。 
  
- `do-while` ループ
  
- `while` ループ
  
- **for** ループ
  
- **for/in** ループ
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- **continue** ステートメントは以下の本体内にのみ表示されます。 
  
  - `do-while` ループ

  - `while` ループ

  - **for** ループ

  - **for/in** ループ
  
## <a name="see-also"></a>関連項目  
 [continue ステートメント](../../javascript/reference/continue-statement-javascript.md)   
 [プログラム フローの制御](../../javascript/controlling-program-flow-javascript.md)   
 [スクリプトのトラブルシューティング](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)
