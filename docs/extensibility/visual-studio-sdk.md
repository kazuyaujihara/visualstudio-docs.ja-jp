---
title: Visual Studio SDK |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VSSDK.v90.StartPage
helpviewer_keywords:
- Visual Studio SDK
- VS SDK (see Visual Studio SDK)
- Visual Studio, SDK
ms.assetid: 1f7c348a-114c-4243-b392-3531e9c9c6fd
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 662b64f69b278c4cc815a742c5cba26592e000bd
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73189089"
---
# <a name="visual-studio-sdk"></a>Visual Studio SDK
Visual studio SDK を使用すると、visual Studio の機能を拡張したり、新しい機能を Visual Studio に統合したりできます。 拡張機能は、他のユーザーや Visual Studio Marketplace にも配布できます。 Visual Studio を拡張する方法の一部を次に示します。

- コマンド、ボタン、メニュー、およびその他の UI 要素を IDE に追加する

- 新しい機能を使用するためのツールウィンドウの追加

- 指定された言語の IntelliSense を拡張するか、新しいプログラミング言語に IntelliSense を提供します

- ライト電球を使用して、開発者がより適切なコードを記述するのに役立つヒントと提案を提供します。

- 新しい言語のサポートを有効にする

- カスタムプロジェクトの種類を追加する

- Visual Studio Marketplace を通じて何百万もの開発者にリーチ

  以前に Visual Studio の拡張機能を作成したことがない場合は、これらの機能の詳細を確認し、 [Visual studio 拡張機能の開発を開始](../extensibility/starting-to-develop-visual-studio-extensions.md)する必要があります。

## <a name="install-the-visual-studio-sdk"></a>Visual Studio SDK のインストール
 Visual Studio SDK は、Visual Studio セットアップのオプション機能です。 VS SDK は、後でインストールすることもできます。 詳細については、「 [Visual STUDIO SDK のインストール](../extensibility/installing-the-visual-studio-sdk.md)」を参照してください。

## <a name="whats-new-in-the-visual-studio-2017-sdk"></a>Visual Studio 2017 SDK の新機能
 Visual Studio SDK には、VSIX v3 形式や互換性に影響する変更点など、いくつかの新機能があり、拡張機能の更新が必要になる場合があります。 詳細については、「 [Visual Studio 2017 SDK の新機能](../extensibility/what-s-new-in-the-visual-studio-2017-sdk.md)」を参照してください。

## <a name="visual-studio-user-experience-guidelines"></a>Visual Studio ユーザーエクスペリエンスガイドライン
 [Visual Studio のユーザーエクスペリエンスガイドライン](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md)で、拡張機能の UI を設計するためのヒントを入手します。

 また、高 DPI デバイス[での拡張](../extensibility/addressing-dpi-issues2.md)機能の外観を確認する方法についても説明します。

 [イメージサービスとカタログ](../extensibility/image-service-and-catalog.md)を活用して、優れたイメージ管理と高 DPI とテーマのサポートを実現します。

## <a name="find-and-install-existing-visual-studio-extensions"></a>既存の Visual Studio 拡張機能を検索してインストールする
 Visual Studio 拡張機能は、 **[ツール]** メニューの **[拡張機能と更新プログラム]** ダイアログで確認できます。 詳細については、「 [Visual Studio 拡張機能の検索と使用](../ide/finding-and-using-visual-studio-extensions.md)」を参照してください。 また、 [Visual Studio Marketplace](https://marketplace.visualstudio.com/)で拡張機能を検索することもできます。

## <a name="visual-studio-sdk-reference"></a>Visual Studio SDK リファレンス
 Visual studio sdk API リファレンスについては、「 [Visual STUDIO Sdk リファレンス](../extensibility/visual-studio-sdk-reference.md)」を参照してください。

## <a name="visual-studio-sdk-samples"></a>Visual Studio SDK のサンプル
 VS SDK 拡張機能のオープンソースの例については、GitHub の「 [Visual Studio のサンプル](https://aka.ms/vs2015sdksamples)」を参照してください。 この GitHub リポジトリには、Visual Studio のさまざまな拡張機能を示すサンプルが含まれています。

## <a name="other-visual-studio-sdk-resources"></a>その他の Visual Studio SDK リソース
 VSSDK に関する質問がある場合、または拡張機能の開発経験を共有する場合は、 [Visual Studio 機能拡張フォーラム](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=vsx)または[ExtendVS Gitter チャットルーム](https://gitter.im/Microsoft/extendvs)を使用できます。

 詳細については、 [VSX Arcana ブログ](https://blogs.msdn.microsoft.com/vsx/)と、Microsoft mvp によって作成された多数のブログを参照してください。

- [お気に入りの Visual Studio 拡張機能](https://scottdorman.blog/2014/10/05/favorite-visual-studio-extensions/)

- [Visual Studio の機能拡張](http://www.visualstudioextensibility.com/overview/vs/)

- [拡張 (Visual Studio を)](https://blog.slaks.net/2013-10-18/extending-visual-studio-part-1-getting-started/)

## <a name="see-also"></a>関連項目

- [メニューコマンドを使用して拡張機能を作成する](../extensibility/creating-an-extension-with-a-menu-command.md)
- [方法: 機能拡張プロジェクトを Visual Studio 2017 に移行する](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md)
- [FAQ: アドインを VSPackage 拡張機能に変換する](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md)
- [マネージコード内の複数のスレッドを管理する](../extensibility/managing-multiple-threads-in-managed-code.md)
- [メニューとコマンドを拡張する](../extensibility/extending-menus-and-commands.md)
- [ツールバーにコマンドを追加する](../extensibility/adding-commands-to-toolbars.md)
- [ツールウィンドウの拡張とカスタマイズ](../extensibility/extending-and-customizing-tool-windows.md)
- [エディターと言語サービスの拡張機能](../extensibility/editor-and-language-service-extensions.md)
- [プロジェクトの拡張](../extensibility/extending-projects.md)
- [ユーザー設定とオプションの拡張](../extensibility/extending-user-settings-and-options.md)
- [カスタムプロジェクトと項目テンプレートの作成](../extensibility/creating-custom-project-and-item-templates.md)
- [プロパティとプロパティウィンドウの拡張](../extensibility/extending-properties-and-the-property-window.md)
- [Visual Studio の他の部分を拡張する](../extensibility/extending-other-parts-of-visual-studio.md)
- [サービスの使用と提供](../extensibility/using-and-providing-services.md)
- [Vspackage の管理](../extensibility/managing-vspackages.md)
- [Visual Studio 分離シェル](https://visualstudio.microsoft.com/vs/older-downloads/isolated-shell/)
- [Visual Studio 拡張機能を出荷する](../extensibility/shipping-visual-studio-extensions.md)
- [Visual Studio SDK の内部](../extensibility/internals/inside-the-visual-studio-sdk.md)
- [Visual Studio SDK のサポート](../extensibility/support-for-the-visual-studio-sdk.md)
- [Visual Studio SDK リファレンス](../extensibility/visual-studio-sdk-reference.md)
