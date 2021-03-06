---
title: '方法: 発行ウィザードを使用して ClickOnce アプリケーションの発行 |Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, publishing
- deploying applications [ClickOnce], Publish wizard
- Windows applications, ClickOnce deployments
- publishing, ClickOnce
ms.assetid: 2e4aa67c-4445-4f7b-9e03-9acb95829127
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: f8708658e5daf90e24a0336040ba2b766d5ae975
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49862828"
---
# <a name="how-to-publish-a-clickonce-application-using-the-publish-wizard"></a>方法: 発行ウィザードを使用して ClickOnce アプリケーションを発行する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ユーザーが ClickOnce アプリケーションを利用できるようにするには、アプリケーションをファイル共有やパス、FTP サーバー、またはリムーバブル メディアに発行する必要があります。 発行ウィザードを使用して、アプリケーションを発行することができます。発行に関連する追加のプロパティが 利用可能な**発行**のページ、**プロジェクト デザイナー**します。 詳細については、次を参照してください。 [ClickOnce アプリケーションの発行](../deployment/publishing-clickonce-applications.md)します。  
  
 発行ウィザードを実行する前に、発行プロパティを適切に設定する必要があります。 たとえば、ClickOnce アプリケーションの署名にキーを指定する場合は、行うことができますなど、**署名**のページ、**プロジェクト デザイナー**します。 詳細については、「[ClickOnce アプリケーションの発行](../deployment/securing-clickonce-applications.md)」を参照してください。  
  
> [!NOTE]
>  ClickOnce を使用してアプリケーションの複数のバージョンをインストールすると、以前のバージョンのアプリケーションは、指定した発行場所の Archive というフォルダーに移されます。 以前のバージョンがこのようにアーカイブされることで、インストール ディレクトリが以前のバージョンのフォルダーから分離されます。  
  
> [!NOTE]
>  使用している設定またはエディションによっては、ヘルプの記載と異なるダイアログ ボックスやメニュー コマンドが表示される場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「 [Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
### <a name="to-publish-to-a-file-share-or-path"></a>ファイル共有またはパスに発行するには  
  
1. **ソリューション エクスプ ローラー**、アプリケーション プロジェクトを選択します。  
  
2. **ビルド** メニューのをクリックして**発行**`Projectname`します。  
  
    発行ウィザードが表示されます。  
  
3. **アプリケーションを発行する場所ですか?**  ページで有効な FTP サーバー アドレスまたは表示形式のいずれかを使用して有効なファイル パスを入力してをクリックし、 **次へ**します。  
  
4. **ユーザーがアプリケーションをインストールする方法でしょうか。**  ページで、ユーザーは、アプリケーションのインストールに移動する場所の場所を選択します。  
  
   -   ユーザーが Web サイトからインストールする場合はクリックして**Web サイトから**前の手順で入力したファイル パスに対応する URL を入力します。 **[次へ]** をクリックします。 (このオプションは通常、発行場所として FTP アドレスを指定する場合に使用します。 FTP からの直接ダウンロードはサポートされていません。 したがって、ここに URL を入力する必要があります。)  
  
   -   ユーザーは、ファイル共有から直接アプリケーションをインストールする場合はクリックして**UNC パスまたはファイル共有**、順にクリックします**次**。 (これはフォーム c:\deploy\myapp の発行場所または\\\server\myapp)。  
  
   -   ユーザーがリムーバブル メディアからインストールする場合はクリックして**から CD-ROM または DVD-ROM**、順にクリックします**次**します。  
  
5. **アプリケーションはオフラインでも利用できますか?**  ページで、適切なオプションをクリックします。  
  
   - 実行するアプリケーションを有効にする場合と、ユーザーがネットワークから切断 をクリックして**はい、このアプリケーションはオンラインでもオフラインでも利用できます**します。 上のショートカット、**開始**アプリケーションのメニューに作成されます。  
  
   - 発行場所から直接アプリケーションを実行する場合は、クリックして**いいえ、このアプリケーションは使用可能なオンラインでのみ**します。 上のショートカット、**開始**メニューは作成されません。  
  
     **[次へ]** をクリックして、続行します。  
  
6. クリックして**完了**アプリケーションを発行します。  
  
    状態通知領域に発行ステータスが表示されます。  
  
### <a name="to-publish-to-a-cd-rom-or-dvd-rom"></a>CD-ROM や DVD-ROM に発行するには  
  
1. **ソリューション エクスプ ローラー**アプリケーション プロジェクトを右クリックし、クリックして、**プロパティ**します。  
  
    **プロジェクト デザイナー**が表示されます。  
  
2. をクリックして、**発行**タブを開く、**発行**ページで、**プロジェクト デザイナー**、 をクリックし、**発行ウィザード**ボタン。  
  
    発行ウィザードが表示されます。  
  
3. **アプリケーションを発行する場所ですか?** ページで、ファイル パスまたは FTP の場所に、アプリケーションの発行先、たとえば d:\deploy を入力します。 クリックして **[次へ]** を続行します。  
  
4. **ユーザーがアプリケーションをインストールする方法でしょうか。**  ページで、 をクリック、 **CD-ROM または DVD-ROM**、順にクリックします**次**。  
  
   > [!NOTE]
   >  インストールが自動的に実行する場合、CD-ROM が挿入されると、開いているドライブに、**発行**ページで、**プロジェクト デザイナー** ] をクリックし、**オプション**ボタン、[、**発行オプション**ウィザードで、**の CD のインストールは、CD が挿入されたときに自動的にセットアップを開始**。  
  
5. アプリケーションを CD-ROM で配布する場合は、Web サイトで更新プログラムを提供する必要が生じることがあります。 **場所は、アプリケーション更新プログラムを確認しますか?**  ページで、更新オプションを選択。  
  
   - 場合は、アプリケーションは更新プログラムの確認 をクリックして**アプリケーションは、次の場所から更新プログラムの確認は**し更新を投稿する場所を入力します。 ファイルの場所、Web サイト、または FTP サーバーを指定できます。  
  
   - アプリケーションは、更新プログラムのチェックは場合に、クリックします**更新プログラム、アプリケーションは確認されません**します。  
  
     **[次へ]** をクリックして、続行します。  
  
6. クリックして**完了**アプリケーションを発行します。  
  
    状態通知領域に発行ステータスが表示されます。  
  
   > [!NOTE]
   >  発行が完了したら、CD-Rewriter または DVD-Rewriter を使用して、手順 3. で指定した場所にあるファイルを CD-ROM メディアまたは DVD-ROM メディアにコピーする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [ClickOnce のセキュリティと配置](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce アプリケーションのセキュリティ](../deployment/securing-clickonce-applications.md)   
 [ClickOnce を使用した Office ソリューションの配置](http://msdn.microsoft.com/library/feb516b3-5e4d-449a-9fd2-347d08d90252)



