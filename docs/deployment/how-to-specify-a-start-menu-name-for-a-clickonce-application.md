---
title: '方法: ClickOnce アプリケーションのスタート メニューの名前を指定します |。Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Start menu resource name
- Start menu name
- ClickOnce deployment, Start menu name
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4ef1675480182796e1fe8bbe29baa5ed6a9d5f63
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62898803"
---
# <a name="how-to-specify-a-start-menu-name-for-a-clickonce-application"></a>方法: ClickOnce アプリケーションのスタート メニューの名前を指定する
オンラインまたはオフラインで利用できる [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] アプリケーションがインストールされると、**スタート**メニューおよび**プログラムの追加と削除** の一覧にエントリが追加されます。 既定では、表示される名前はアプリケーション アセンブリの名前と同じですが、**発行オプション** のダイアログ ボックスで**製品名**を設定することで表示名を変更することがきます。

 **製品名**に表示される、 *publish.htm*ページは、インストールされているオフライン アプリケーション内のエントリの名前をことが、**開始** メニューともなりますに表示される名前**を追加または削除プログラム**します。

 **発行元名**に表示されます、 *publish.htm*ページ上部**製品名**、オフライン アプリケーションのインストールされている場合も可能になりますを含む、アプリケーションのフォルダーの名前とアイコン、**開始**メニュー。

 スタート メニュー ショートカットまたはアプリ参照が作成される *%appdata%\Microsoft\Windows\Start menu \programs\\< 発行者名\>* します。 ショートカットまたはアプリの参照は、製品名と同じ名前を持ちます。

 **製品名**と**パブリッシャー名**のプロパティは、**プロジェクト デザイナー**の**発行**ページにある**発行オプション** ダイアログ ボックスで設定することができます。

### <a name="to-specify-a-start-menu-name"></a>スタート メニューの名前を指定するには

1. **ソリューション エクスプ ローラー**でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。

2. **発行**タブをクリックします。

3. **オプション**ボタンをクリックして、**発行オプション** ダイアログ ボックスを開きます。

4. **説明**をクリックします。

5. **発行オプション** ダイアログ ボックスで、**製品名**に表示する名前を入力します。

6. 必要に応じて、**パブリッシャー名**にパブリッシャー名を入力します。

## <a name="see-also"></a>関連項目
- [ClickOnce アプリケーションの発行](../deployment/publishing-clickonce-applications.md)
- [方法: 発行ウィザードを使用して ClickOnce アプリケーションを発行する](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)