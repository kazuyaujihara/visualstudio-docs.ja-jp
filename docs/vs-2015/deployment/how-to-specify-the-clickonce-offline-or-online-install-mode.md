---
title: '方法: 指定の ClickOnce のオフラインまたはオンライン モードのインストール |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, specifying install mode
- install mode
- online applications
- offline applications
- ClickOnce install mode
ms.assetid: 0aee5fc1-e966-4bda-9b8f-d9997aeaa779
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d4111ca5aee4a405a4a797dbfee14a3d4b50435f
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60054252"
---
# <a name="how-to-specify-the-clickonce-offline-or-online-install-mode"></a>方法: ClickOnce のオフラインまたはオンラインのインストール モードを指定する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`Install Mode`の[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]アプリケーションがオフラインまたはオンライン、アプリケーションが利用できるかどうかを判断します。 選択すると**アプリケーションはオンラインでのみ使用可能な**に、ユーザーがアクセスする必要があります、[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]発行場所 (Web ページまたはファイル共有のいずれか)、アプリケーションを実行するためにします。 選択すると**アプリケーションはオフラインでも利用可能な**、アプリケーションへのエントリを追加します、**開始**メニューと**プログラム追加と削除** ダイアログ ボックスは、ユーザーは、接続されていないときに、アプリケーションを実行することができます。  
  
 `Install Mode`に設定することができます、**発行**のページ、**プロジェクト デザイナー**します。  
  
 **注**、`Install Mode`発行ウィザードを使用して設定できます。 詳細については、「[方法 :発行ウィザードを使用して ClickOnce アプリケーションを発行する](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)」を参照してください。  
  
### <a name="to-make-a-clickonce-application-available-online-only"></a>ClickOnce アプリケーションを使用できるようにするオンラインのみ  
  
1. **ソリューション エクスプ ローラー**でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。  
  
2. **発行**タブをクリックします。  
  
3. **モードのインストールと設定**領域で、をクリックして、**アプリケーションはオンラインでのみ使用可能な**オプション ボタンをクリックします。  
  
### <a name="to-make-a-clickonce-application-available-online-or-offline"></a>オンラインまたはオフラインのために、ClickOnce アプリケーションを使用できるようにするには  
  
1. **ソリューション エクスプ ローラー**でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。  
  
2. **発行**タブをクリックします。  
  
3. **モードのインストールと設定**領域で、をクリックして、**アプリケーションはオフラインでも利用可能な**オプション ボタンをクリックします。  
  
     アプリケーションにエントリを追加インストールすると、**開始**メニューと**プログラム追加と削除**コントロール パネルの します。  
  
## <a name="see-also"></a>関連項目  
 [ClickOnce アプリケーションの発行](../deployment/publishing-clickonce-applications.md)   
 [方法: 発行ウィザードを使用して ClickOnce アプリケーションを発行します。](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [ClickOnce 配置ストラテジの選択](../deployment/choosing-a-clickonce-deployment-strategy.md)
