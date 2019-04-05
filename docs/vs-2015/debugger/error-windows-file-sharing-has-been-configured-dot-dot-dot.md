---
title: エラー :Windows ファイル共有が構成されました... |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.remote_credentials_prohibited
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: c45a1b74-61ec-4c64-9e2c-13051a4f50a5
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7664c94f626b639f4d0330b938777d545128847d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977961"
---
# <a name="error-windows-file-sharing-has-been-configured"></a>エラー :Windows ファイル共有が構成されました...
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

別のユーザー名を使用してリモート コンピューターに接続できるように Windows ファイル共有が構成されました。 この設定はリモート デバッグと互換性がありません。  
  
 現在のファイル共有の構成は、別のユーザー名を使用してリモート コンピューターに接続するようにセットアップされています。 このシナリオでは、リモート デバッグを実行できません。  
  
 このエラーを解決するには、他のアカウント名を使用してコンピューターにログオンするか、デバッグを実行しているアカウント名を使用するようにファイル共有を変更します。  
  
 このユーザー名を使用してリモート コンピューターに接続する場合は、まずリモート コンピューターから切断する必要があります。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  他のアカウント名を使用してローカル コンピューター (デバッグを起動したコンピューター) にログオンします。  
  
     または  
  
     . リモート コンピューターから切断します。次に、自分のアカウント名を使用して他のコンピューターに接続するようにファイル共有を再構成します。  
  
    1.  **[スタート]** メニューの **[アクセサリ]** をポイントして、**[コマンド プロンプト]** をクリックします。  
  
    2.  Windows のコマンド プロンプトで、次のように入力します。  
  
         `net use /delete computer_name`  
  
    3.  Windows ヘルプに記載されているいずれかの方法を使用して、ファイル共有の設定を変更します。
