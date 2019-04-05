---
title: エラー :マシンに接続できません&lt;名前&gt;します。 ネットワーク上にコンピューターが見つかりません。 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.remote.dcom_disabled
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- DCOM, unable to connect error
ms.assetid: b584b5db-ef52-45ed-8561-1314da3cc5b8
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 151025ceb36715c1ac3269c5cfd55eba14685c8c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58962346"
---
# <a name="error-unable-to-connect-to-the-machine-ltnamegt-the-machine-cannot-be-found-on-the-network"></a>エラー :マシンに接続できません&lt;名前&gt;します。 ネットワーク上にコンピューターが見つかりません。
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このエラーは、次の条件のいずれかが満たされると発生します。  
  
-   リモート コンピューターへの接続が解除された。  
  
-   リモート コンピューターのユーザー アカウントが無効になっている。  
  
-   リモート コンピューターのパスワードの有効期限が切れている。  
  
### <a name="to-resolve-this-behavior"></a>この問題を解決するには  
  
-   ローカル コンピューターとリモート コンピューターが同じネットワーク上に存在することを確認します。 これを行うには、Microsoft Windows エクスプローラー (ファイル エクスプローラー) を使用してリモート コンピューターにアクセスしてみます。  
  
     および  
  
-   リモート コンピューターへの接続に使用しているユーザー アカウントが有効になっていることを確認します。  
  
     および  
  
-   リモート コンピューターへの接続に使用しているパスワードが有効であり、有効期限が切れていないことを確認します。  
  
## <a name="see-also"></a>関連項目  
 [デバイスのリモート ツールをセットアップします。](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)   
 [デバッガーの設定と準備](../debugger/debugger-settings-and-preparation.md)
