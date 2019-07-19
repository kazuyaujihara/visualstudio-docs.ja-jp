---
title: Evaluate Statement コマンド | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f774458eb63d9e56b99a635e7b32309375a903ef
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199359"
---
# <a name="evaluate-statement-command"></a>Evaluate Statement コマンド
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

指定したステートメントを評価し、表示します。  
  
## <a name="syntax"></a>構文  
  
```  
Debug.EvaluateStatement text   
```  
  
## <a name="arguments"></a>引数  
 `text`  
 必須です。 評価するステートメント。  
  
## <a name="remarks"></a>解説  
 **EvaluateStatement** コマンドをどのウィンドウに入力するかによって、等号 (=) を比較演算子として解釈するのか、代入演算子として解釈するのかが決まります。  
  
 **[コマンド]** ウィンドウの場合、等号 (=) は、比較演算子と解釈されます。 したがって、たとえば変数 `a` と変数 `b` の値が異なる場合、次のコマンド  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 は、値 `false` を返します。  
  
 一方、 **[イミディエイト]** ウィンドウの場合、等号 (=) は、代入演算子と解釈されます。 したがって、たとえば次のコマンド  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 では、変数 `a` に変数 `b` の値が代入されます。  
  
## <a name="example"></a>例  
  
```  
>Debug.EvaluateStatement(a+b)  
```  
  
## <a name="see-also"></a>関連項目  
 [Print コマンド](../../ide/reference/print-command.md)   
 [Visual Studio のコマンド](../../ide/reference/visual-studio-commands.md)   
 [コマンド ウィンドウ](../../ide/reference/command-window.md)   
 [[検索/コマンド] ボックス](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
