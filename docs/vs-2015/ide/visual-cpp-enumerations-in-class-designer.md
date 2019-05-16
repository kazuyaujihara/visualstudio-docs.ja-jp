---
title: クラス デザイナーの Visual C++ 列挙体 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b38d36c1fdc0033115f1d7a4cf18265dc1f2a3ab
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65696359"
---
# <a name="visual-c-enumerations-in-class-designer"></a>クラス デザイナーの Visual C++ 列挙体
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

クラス デザイナーでは、C++ の `enum`、およびスコープを持つ `enum class` 型はサポートされていません。 例を次に示します。  
  
```  
enum CardSuit {  
   Diamonds = 1,  
   Hearts = 2,  
   Clubs = 3,  
   Spades = 4  
};  
  
// or...  
enum class CardSuit {  
   Diamonds = 1,  
   Hearts = 2,  
   Clubs = 3,  
   Spades = 4  
};  
  
```  
  
 クラス ダイアグラムにおける C++ 列挙体の図形の形状と動作は構造体の図形に似ていますが、ラベルが **[Enum]** または **[Enum class]** である点と、青ではなくピンクである点、および左と上の余白に色つきの枠がある点が異なります。 列挙体の図形も構造体の図形も、角が直角になっています。  
  
 `enum` 型の使用法の詳細については、「[列挙型](https://msdn.microsoft.com/library/081829db-5dca-411e-a53c-bffef315bcb3)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ コードの使用 (クラス デザイナー)](../ide/working-with-visual-cpp-code-class-designer.md)   
 [列挙型](https://msdn.microsoft.com/library/081829db-5dca-411e-a53c-bffef315bcb3)
