---
title: -Diff | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
ms.assetid: 5377fedb-632a-4e86-a947-7c11c86451e7
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: a7e7d7c7a7fba122f62dd3edb7cdac2b6e175167
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59666391"
---
# <a name="diff"></a>/Diff
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

2 つのファイルを比較します。 相違点は特殊な Visual Studio のウィンドウに表示されます。  
  
## <a name="syntax"></a>構文  
  
```  
devenv /Diff SourceFile, TargetFile, [SourceDisplayName],[TargetDisplayName]  
```  
  
## <a name="arguments"></a>引数  
 `SourceFile`  
 必須。 比較する最初のファイルの完全パスと名前。  
  
 `TargetFile`  
 必須。 比較する 2 番目のファイルの完全パスと名前。  
  
 `SourceDisplayName`  
 任意。 最初のファイルの表示名。  
  
 `TargetDisplayName`  
 省略可能です。 2 番目のファイルの表示名。
