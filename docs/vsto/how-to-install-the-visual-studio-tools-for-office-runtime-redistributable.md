---
title: '方法: Visual Studio Tools for Office ランタイム再頒布可能パッケージをインストールする方法'
titleSuffix: ''
ms.custom: seodec18
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office runtime [Office development in Visual Studio]
- installing Office development tools in Visual Studio
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5d9bb53fbdc3d6766dab47c654f0a43ad902b2f3
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551832"
---
# <a name="how-to-install-the-visual-studio-tools-for-office-runtime-redistributable"></a>方法: Visual Studio Tools for Office ランタイム再頒布可能パッケージをインストールする方法
  Visual Studio 2010 Tools for Office ランタイムは、[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] の中で Microsoft Office developer tools を使用して作成されたソリューションを実行する各コンピューターにインストールする必要があります。 ランタイムは、[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]、および Microsoft Office をインストールすると自動的にインストールされます。 詳細については、[Visual Studio Tools for Office runtime のインストール シナリオ](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)を参照してください。

[!include[Add-ins note](includes/addinsnote.md)]

 次の場合は、手動による以下のインストール手順を実行する必要があります。

- [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] をサーバーにインストールする必要がある場合。 たとえば、サーバー上のドキュメント レベルのソリューションを管理する <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> クラスを使用する場合です。

- Office ソリューションのその他の必須コンポーネントが既にインストールされているコンピューターにランタイムをインストールする必要がある場合。

    > [!NOTE]
    > .NET Framework および [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] をインストールするには、開発コンピューターの管理者である必要があります。

## <a name="to-install-the-visual-studio-tools-for-office-runtime"></a>Visual Studio Tools for Office ランタイムをインストールするには

1. [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 以降をインストールします。

    - [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]をダウンロードするには、[Microsoft .NET Framework 4 (Web インストーラー)](http://go.microsoft.com/fwlink/?LinkId=178957)を参照してください。

    - [!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)]をダウンロードするには、[Microsoft .NET Framework 4 Client Profile (Web インストーラー)](http://go.microsoft.com/fwlink/?LinkId=178958)を参照してください。

    - [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]をダウンロードするには、[Microsoft .NET Framework 4.5](http://www.microsoft.com/download/details.aspx?id=30653)を参照してください。

2. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]をインストールするには、*vstor_redist.exe* を実行します。

     これらのセットアップ ファイルは、[Visual Studio 2010 Tools for Office ランタイム](http://go.microsoft.com/fwlink/?LinkId=140384)からダウンロードできます。 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] の必須コンポーネントは .NET Framework の場合と同じです。

     [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] には、言語パックが用意されています。 Windows のインストールが英語以外の言語に設定されている場合、Windows と同じ言語でランタイム メッセージを表示できます。 同様に、エンド ユーザーが [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] をインストールし、英語以外の言語に設定されている Windows のインストールでソリューションを実行すると、Windows と同じ言語でランタイム メッセージが表示されます。 場合によっては、追加の言語パックが必要になる場合があります。 たとえば、Windows のコピーが 1 つ以上の言語設定を使用したり、[!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]が既にインストールされた後に別の言語に切り替える場合は、追加の言語パックが必要になることがあります。 言語パックは、[Microsoft Visual Studio 2010 Tools for Microsoft Office system (バージョン 4.0 ランタイム) language pack](http://go.microsoft.com/fwlink/?LinkId=140386)で見つかります。

## <a name="see-also"></a>関連項目
- [はじめに &#40;Visual Studio での Office 開発&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [Office ソリューションの開発コンピューターの構成](../vsto/configuring-a-computer-to-develop-office-solutions.md)
- [方法: Office ソリューションを開発するコンピューターを構成する方法](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)
- [方法: Office プライマリ相互運用機能アセンブリをインストールする方法](../vsto/how-to-install-office-primary-interop-assemblies.md)
- [ServerDocument クラスを使用してサーバー上のドキュメントを管理する](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)
- [Office ソリューションのデプロイ](../vsto/deploying-an-office-solution.md)
