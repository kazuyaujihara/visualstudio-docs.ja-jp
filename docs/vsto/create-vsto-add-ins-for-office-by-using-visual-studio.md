---
title: Visual Studio を使用して Office 用 VSTO アドインを作成する
titleSuffix: ''
ms.custom: seodec18
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e64d97b948f38b4c9b5943d5e561aa865d4f765f
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551667"
---
# <a name="create-vsto-add-ins-for-office-by-using-visual-studio"></a>Visual Studio を使用して Office 用 VSTO アドインを作成する
  Visual Studio の Microsoft Office Developer Tools を使用して、Office を拡張する .NET Framework アプリケーションを作成できます。 このようなアプリケーションは、 *Office ソリューション*とも呼ばれます。

 Office Developer Tools で提供される機能は、さまざまなビジネス要件に合った Office ソリューションを作成するのに役立ちます。 このツールには、Visual Basic または Visual C# を使用した Office ソリューションの作成に役立つプロジェクト テンプレートや、Office ソリューションで使用するカスタム ユーザー インターフェイスの作成に役立つビジュアルなデザイナーが含まれています。

[!include[Add-ins note](includes/addinsnote.md)]

 Office 開発の最新情報については、MSDN の次のデベロッパー センターを参照してください。

- [Visual Studio の開発者ポータルでの Office 開発](http://go.microsoft.com/fwlink/?LinkId=123844)には、製品情報、コード サンプル、ビデオに加え、Visual Studio を使用して、Office アプリケーションをソリューションの一部としてカスタマイズする方法のコミュニティ リソースへのリンクが含まれています。

- [Microsoft Office デベロッパー センター](http://go.microsoft.com/fwlink/?LinkId=83467)には、技術記事、コード サンプル、ダウンロード、コミュニティ情報、サポート、および Office のカスタマイズと Office Business Application (OBA) に関する他のドキュメントへのリンクが含まれています。

## <a name="in-this-section"></a>このセクションの内容
- [はじめに&#40;Visual Studio での Office 開発&#41;](../vsto/getting-started-office-development-in-visual-studio.md)

 Office ソリューションの作成用に開発コンピューターを構成する方法、Office ソリューションの作成を開始する方法、および Visual Studio での Office 開発を対象とする新機能に関する情報へのリンクを示します。

- [Office ソリューションのアップグレードと移行](../vsto/upgrading-and-migrating-office-solutions.md)

 Visual Studio の以前のバージョンを使用して作成されたプロジェクトのアップグレード プロセスに関する情報へのリンクを示します。

- [Visual Studio での Office ソリューションのアーキテクチャ](../vsto/architecture-of-office-solutions-in-visual-studio.md)

 ドキュメント レベルのカスタマイズと VSTO アドインに関する情報など、Office ソリューションの動作に関する情報へのリンクを示します。

- [Office ソリューションの設計と作成](../vsto/designing-and-creating-office-solutions.md)

 Visual Studio で Office プロジェクトを作成し、プロジェクトを構成する方法について説明します。

- [Office ソリューションの開発](../vsto/developing-office-solutions.md)

 Office ユーザー インターフェイスをカスタマイズする方法、データを処理する方法、問題のトラブルシューティングを行う方法など、Office ソリューションでマネージド コードを使用する方法について説明します。

- [Excel ソリューション](../vsto/excel-solutions.md)

 Excel を自動化する方法、Excel ソリューションを作成する方法、および Excel に固有のグローバリゼーションに関する問題を理解する方法について説明します。

- [InfoPath ソリューション](../vsto/infopath-solutions.md)

 InfoPath のフォーム テンプレートおよび VSTO アドインを作成する方法について説明します。

- [Outlook ソリューション](../vsto/outlook-solutions.md)

 Outlook を自動化し、Outlook VSTO アドインおよびフォーム領域を作成する方法について説明します。

- [PowerPoint ソリューション](../vsto/powerpoint-solutions.md)

 PowerPoint を自動化し、PowerPoint VSTO アドインを作成する方法について説明します。

- [Project ソリューション](../vsto/project-solutions.md)

 Microsoft Office Project の自動化および VSTO アドイン プロジェクトを作成する方法について説明します。

- [Visio ソリューション](../vsto/visio-solutions.md)

 Visio を自動化し、Visio VSTO アドインを作成する方法について説明します。

- [Word ソリューション](../vsto/word-solutions.md)

 Word を自動化し、Word ソリューションを作成する方法について説明します。

- [Office ソリューションの構築](../vsto/building-office-solutions.md)

 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]における、Office プロジェクトのビルドと、その他の種類のプロジェクトのビルドとの間の相違点について説明します。

- [Office プロジェクトのデバッグ](../vsto/debugging-office-projects.md)

 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]における、Office プロジェクトのデバッグと、その他の種類のプロジェクトのデバッグとの間の相違点について説明します。

- [セキュリティで保護された Office ソリューション](../vsto/securing-office-solutions.md)

 Office ソリューションにおけるセキュリティ機能のしくみについて説明します。

- [Office ソリューションのデプロイ](../vsto/deploying-an-office-solution.md)

 Office ソリューションをユーザーが使用できるようにする方法、および配置方法を選択するときに考慮する主な問題点について説明します。

- [Office 開発のサンプルとチュートリアル](../vsto/office-development-samples-and-walkthroughs.md)

 サンプル アプリケーション、および一般的なタスクの詳細な手順を説明するトピックへのリンクを示します。

- [一般的な&#40;リファレンス (Visual Studio での Office 開発)&#41;](../vsto/general-reference-office-development-in-visual-studio.md)

 Office プライマリ相互運用機能アセンブリ、マニフェスト、ユーザーインターフェイス要素、およびエラーメッセージに関する詳細情報へのリンクを示します。

- [Visual Studio &#40;でのマネージリファレンス Office 開発&#41;](../vsto/managed-reference-office-development-in-visual-studio.md)

 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] を対象とする Office プロジェクトで使用される API の名前空間と型に関する情報へのリンクを示します。 .NET Framework 3.5 を対象とする Office プロジェクトで使用されている名前空間と型に関する API リファレンス ドキュメントは、Visual Studio 2008 ドキュメントのリファレンス セクション [2007 system マネージ参照](http://go.microsoft.com/fwlink/?LinkId=160658)を参照してください。

- [Visual Studio で&#40;のアンマネージ API リファレンス Office 開発&#41;](../vsto/unmanaged-api-reference-office-development-in-visual-studio.md)

 Office アプリケーションでマネージド VSTO アドインのロードとアンロードなどの操作を実行するために使用できる COM インターフェイスに関する情報へのリンクを示します。

## <a name="related-sections"></a>関連項目
- [Visual Studio 開発者ポータルを使用した Office 開発](http://go.microsoft.com/fwlink/?LinkId=123844)技術記事、ビデオ、ブログなど、その他のリソースを提供します。

- [Visual Studio デベロッパーセンター](http://go.microsoft.com/fwlink/?LinkID=99124)技術記事、ビデオ、ブログなど、その他の Visual Studio リソースを提供します。

- [Office Business Applications 開発者ポータル](http://go.microsoft.com/fwlink/?LinkId=99125)Office Business Applications (Oba) に関する情報と、Office system プラットフォームを使用してそれらを構築する方法について説明します。

- [MSDN ライブラリの Microsoft Office 開発](http://go.microsoft.com/fwlink/?LinkId=149870)に関するセクションMSDN ライブラリの領域では、いくつかのバージョンの Office のソリューション開発に関する記事やリファレンスドキュメントを参照できます (Visual Studio を使用した Office 開発に固有ではありません)。

- [Visual Studio でのアプリケーション開発](https://msdn.microsoft.com/97490c1b-a247-41fb-8f2c-bc4c201eff68)Visual Studio を使用して、web アプリケーション、XML web サービス、および従来のクライアントアプリケーションを設計、開発、デバッグ、および配置する方法について説明するトピックへのリンクを示します。

- [Visual Studio でのプログラミングの .NET Framework](/previous-versions/visualstudio/visual-studio-2010/k1s94fta(v=vs.100))Visual Basic とビジュアルC#の .NET Framework を使用したアプリケーション開発について説明します。
