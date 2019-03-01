---
title: '方法: エンドユーザーがからインストールする場所を指定 |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], specifying an installation URL
- URLs, specifying an installation URL
- installation, specifying installation an URL
- Installation URL property
ms.assetid: 04a804bf-ed55-4a7a-a1e6-f63ed99c0276
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2470c6ff8603bc100ee515b046efcf2436cb0b4e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56629132"
---
# <a name="how-to-specify-the-location-where-end-users-will-install-from"></a>方法: エンド ユーザーがインストールを開始する場所を指定する
発行するときに、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]アプリケーションをダウンロードしてインストール、アプリケーションにアクセスするユーザーの場所は必ずしも、アプリケーションを最初に発行する場所。 たとえば、一部の組織で、開発者は、ステージング サーバーにアプリケーションを公開可能性があり、管理者は、アプリケーションを Web サーバーを移動し。

 この場合、使用することができます、`Installation URL`プロパティをユーザーは、アプリケーションのダウンロードにアクセスする Web サーバーを指定します。 これは、機能は、アプリケーション マニフェストが更新プログラムを検索する場所を認識できるように必要です。

 `Installation URL`でプロパティを設定することができます、**発行**のページ、**プロジェクト デザイナー**します。

 **注**、`Installation URL`を使用してプロパティを設定することも、**発行ウィザード**します。 詳細については、次を参照してください。[方法: 発行ウィザードを使用して ClickOnce アプリケーションを発行](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)します。

### <a name="to-specify-an-installation-url"></a>インストール URL を指定するには

1.  **ソリューション エクスプローラー**でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。

2.  **[発行]** タブをクリックします。

3.  インストール URL フィールドに、形式を使用して完全修飾 URL を使用して、インストール場所を入力します*http://www.microsoft.com/ApplicationName*、または UNC パス形式を使用して *\\\Server\ApplicationName*。

## <a name="see-also"></a>関連項目
- [方法: Visual Studio がファイルをコピーする場所を指定する](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)
- [ClickOnce アプリケーションの発行](../deployment/publishing-clickonce-applications.md)
- [方法: 発行ウィザードを使用して ClickOnce アプリケーションを発行する](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)