---
title: '方法: SharePoint の配置コマンドの設定 |Microsoft Docs'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deploying
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 79843389adcd7dc0a4e350e4fd010d450c837a4e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56606694"
---
# <a name="how-to-set-sharepoint-deployment-commands"></a>方法: SharePoint の配置コマンドを設定します。
  配置前や配置後のコマンドを設定して、展開プロセスをカスタマイズできます。 これらのコマンドは、Visual Studio からの SharePoint ソリューションをデバッグするときに前に、と後、その他の展開アクションを実行します。

### <a name="to-add-a-pre-deployment-command"></a>配置前コマンドを追加するには

1.  メニュー バーで、**プロジェクト** > **\<*ProjectName*> プロパティ**します。

2.  選択、 **SharePoint**タブ。

3.  **配置前コマンドライン**テキスト ボックスに、このステップをカスタマイズする MS-DOS または MSBuild のコマンドを入力します。

     たとえば、ディレクトリの内容の一覧を表示して、デプロイが完了する前に、次のように入力します。 **dir**します。

### <a name="to-add-a-post-deployment-command"></a>配置後コマンドを追加するには

1.  メニュー バーで、**プロジェクト** > **\<*ProjectName*> プロパティ**します。

2.  選択、 **SharePoint**タブ。

3.  **配置後コマンドライン**テキスト ボックスに、このステップをカスタマイズする MS-DOS または MSBuild のコマンドを入力します。

     たとえば、ディレクトリの内容の一覧を表示して、デプロイが完了した後、次のように入力します。 **dir**します。 MSBuild 変数を使用すると、ビルド ディレクトリから、アセンブリをコピーして、次のように入力します。**コピー $ (targetpath) c:\DeploymentDirectory**します。

## <a name="see-also"></a>関連項目
- [パッケージ化し、SharePoint ソリューションのデプロイ](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)
