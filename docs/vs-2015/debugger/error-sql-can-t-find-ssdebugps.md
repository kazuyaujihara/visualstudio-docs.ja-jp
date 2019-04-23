---
title: エラー :SQL できます&#39;t が SSDEBUGPS を見つける |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.sqlde_cant_find_ssdebugps
dev_langs:
- FSharp
- VB
- CSharp
- C++
- SQL
ms.assetid: 596425c8-14c7-4c05-8823-e1c52f420f5e
caps.latest.revision: 9
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 25462a99bd3e773f03af3918a9e25d11ed006c1c
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60084714"
---
# <a name="error-sql-can39t-find-ssdebugps"></a>エラー :SQL できます&#39;t が SSDEBUGPS を見つける
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

SSDEBUGPS.dll は、SQL Server のデバッグ ホスト コンポーネントです。  
  
 このエラーはデバッグの開始時に発生し、指定されたファイルが [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] コンピューターに存在しないことを示します。 リモート デバッグのセットアップが実行されていない、または何らかの理由でこのファイルが削除されていることが原因として考えられます。  
  
 このエラーの解決方法は 2 つあります。1 つは、リモート デバッグのセットアップを再実行する方法です。もう 1 つは、このファイルを [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] コンピューターにコピーする方法です。  
  
 リモート デバッグのセットアップを再実行する」の手順に従います[リモート デバッグ](../debugger/remote-debugging.md)します。  
  
 ssdebugps.dll のファイルを見つけることができる場合は、これを [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] コンピューターにコピーします。 このファイルが存在する場合は、\Program Files\ Common Files\Microsoft Shared\SQL Debugging にあります。 別のあります[!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)]コンピューターやコンピューターとは[!INCLUDE[vsprvslong](../includes/vsprvslong-md.md)]インストールします。  
  
### <a name="to-copy-ssdebugpsdll-onto-the-sql-server-2005-machine"></a>SSDEBUGPS.dll を SQL Server 2005 コンピューターにコピーするには  
  
1. [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] コンピューターの上記の名前とパスを持つディレクトリにファイルをコピーします。  
  
2. **コマンド プロンプト**を開き、次のコマンドを実行してファイルを登録します。  
  
    ```  
    regsvr32 ssdebugps.dll  
    ```
