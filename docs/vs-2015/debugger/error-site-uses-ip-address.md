---
title: エラー :サイトは IP アドレスの使用 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.webdbg_siteusesipaddress
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
ms.assetid: b2b8ddc8-746d-46e3-87a6-b956b1ee048d
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e040c45079c9e4b82337cbd1e4b5d7d8306e1a32
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58963678"
---
# <a name="error-site-uses-ip-address"></a>エラー :サイトは IP アドレスを使用しています
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このエラーは、IP アドレスを使用している Web アプリケーションに、デバッガーが自動アタッチしようとしたときに発生します。 これは、IIS で **[Web サイトの識別]** を **[特定の IP アドレスを使用]** に変更した場合に発生します。  
  
 自動アタッチが機能するには、コンピューター名だけでなく、IP アドレスを指定したプロジェクトを作成する必要があります。 そうしないと、コンピューター名は localhost に変更されるため、DEBUG 動詞を IIS に送信するときにエラーが発生します。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  手動のアタッチを使用します ([デバッグ] メニューの **[プロセスにアタッチ]** を選択します)。  
  
     または  
  
2.  IIS の **[Web サイトの識別]** 設定を変更します。  
  
## <a name="see-also"></a>関連項目  
 [Web アプリケーションのデバッグ: エラーとトラブルシューティング](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
