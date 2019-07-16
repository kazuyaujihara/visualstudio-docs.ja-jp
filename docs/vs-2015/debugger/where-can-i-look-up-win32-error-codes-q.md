---
title: Win32 のエラー コードを調べるには | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vc.errors
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- error codes, Win32
- Win32, error codes
ms.assetid: 8fb4ff42-b8eb-4152-b49e-b802d194b05e
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d403315a2320589f69174109d55c8726ffd5f673
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68149396"
---
# <a name="where-can-i-look-up-win32-error-codes"></a>Win32 のエラー コードを調べるには
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

WINERROR.H には、Win32 API 関数のエラー コード定義が含まれています。このファイルは、既定のインストールでは INCLUDE ディレクトリにあります。  
  
 エラー コードを検索するには、 **[ウォッチ]** ウィンドウまたは **[クイック ウォッチ]** ダイアログ ボックスに、検索対象のコードを入力します。 例えば:  
  
```  
0x80000004,hr  
```  
  
## <a name="see-also"></a>関連項目  
 [ネイティブ コードのデバッグに関する FAQ](../debugger/debugging-native-code-faqs.md)   
 [ネイティブ コードのデバッグ](../debugger/debugging-native-code.md)
