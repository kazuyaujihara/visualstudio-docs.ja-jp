---
title: Open Solution コマンド | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- file.opensolution
helpviewer_keywords:
- Open Solution command
- File.OpenSolution command
ms.assetid: 61de76c8-69d7-4cdb-b605-e132f45d05d9
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: bb99d359f3858d8e7f15e013ab56719c7ed14995
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199023"
---
# <a name="open-solution-command"></a>OpenSolution コマンド
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

開いている他のソリューションを閉じ、既存のソリューションを開きます。  
  
## <a name="syntax"></a>構文  
  
```  
File.OpenSolution filename  
```  
  
## <a name="arguments"></a>引数  
 `Filename`  
 必須です。 開くソリューションの完全パスとファイル名。  
  
 `filename` 引数の構文の場合、空白を含むパスで引用符を使用する必要があります。  
  
## <a name="remarks"></a>解説  
 オート コンプリートでは、入力された正しいパスとファイル名の検索を試みます。  
  
## <a name="example"></a>例  
 この例では、Test1.sln というソリューションを開きます。  
  
```  
>File.OpenSolution "c:\MySolutions\Test1\Test1.sln"  
```  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio のコマンド](../../ide/reference/visual-studio-commands.md)   
 [コマンド ウィンドウ](../../ide/reference/command-window.md)   
 [[検索/コマンド] ボックス](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
