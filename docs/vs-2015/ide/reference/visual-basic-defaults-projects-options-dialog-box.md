---
title: '[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト]) | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Projects.VBDefaults
helpviewer_keywords:
- Option Explicit statement, setting in the IDE
- Option Compare statement, setting in the IDE
- Option Strict statement, setting in the IDE
ms.assetid: 2465cd9d-18b6-4c4a-b1ea-86dbab23fc79
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e4c8a1b593333c8b560a828bb0edc5fa7f0628b5
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49274860"
---
# <a name="visual-basic-defaults-projects-options-dialog-box"></a>[Visual Basic の既定値] ([オプション] ダイアログ ボックス - [プロジェクト])
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Visual Basic プロジェクトのオプションに対する既定の設定を指定します。 新しいプロジェクトを作成すると、指定したオプション ステートメントがコード エディターのプロジェクト ヘッダーに追加されます。 このオプションは、すべての Visual Basic プロジェクトに適用されます。  
  
 このダイアログ ボックスにアクセスするには、**[ツール]** メニューの **[オプション]** をクリックし、**[プロジェクトおよびソリューション]** フォルダーを展開して、**[Visual Basic の既定値]** をクリックします。  
  
 **Option Explicit**  
 明示的な変数の宣言が必要となるように、コンパイラの既定値を設定します。 既定では、**[Option Explicit]** は **[On]** に設定されています。 詳細については、「[/optionexplicit](http://msdn.microsoft.com/library/5d296ab3-bafe-4c4d-9887-78f162ed86c7)」を参照してください。  
  
 **Option Strict**  
 明示的な縮小変換を必要とし、遅延バインディングが許可されるように、コンパイラの既定値を設定します。 既定では、**[Option Strict]** は **[Off]** に設定されています。 詳細については、「[/optionstrict](http://msdn.microsoft.com/library/c7b10086-0fa4-49db-b3c8-4ae0db5957da)」を参照してください。  
  
 **Option Compare**  
 文字列比較でのコンパイラの既定値を設定します。[binary] (大文字と小文字を区別する) または [text] (大文字と小文字を区別しない) を設定できます。既定では、**[Option Compare]** は **[Binary]** に設定されています。 詳細については、「[/optioncompare](http://msdn.microsoft.com/library/7237b766-b44d-4cc5-9a3c-885348a7d9e4)」を参照してください。  
  
 **Option Infer**  
 ローカル型の推論についてのコンパイラの既定値を設定します。 既定では、新しく作成されたプロジェクトの場合は **[Option Infer]** が **[On]** に設定され、以前のバージョンの Visual Basic で作成されて移行されたプロジェクトの場合は **[Off]** に設定されます。 詳細については、「[/optioninfer](http://msdn.microsoft.com/library/f6c09db1-0553-464a-abe3-d4510c61d6ed)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [ソリューションおよびプロジェクト](../../ide/solutions-and-projects-in-visual-studio.md)



