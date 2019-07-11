---
title: Visual Studio 2019 for Mac をインストールする
description: Visual Studio 2019 for Mac とクロスプラット フォーム開発に必要なその他のコンポーネントをインストールする手順について説明します。
author: asb3993
ms.author: amburns
ms.date: 04/02/2019
ms.technology: vs-ide-install
ms.assetid: 22B1F2CD-32AE-464D-80AC-C8AB4786B015
ms.custom: video
ms.openlocfilehash: 2086532f0602b4a2509358cbb6d57178a9a1a0d4
ms.sourcegitcommit: 7fbfb2a1d43ce72545096c635df2b04496b0be71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "67691462"
---
# <a name="install-visual-studio-2019-for-mac"></a>Visual Studio 2019 for Mac をインストールする

macOS でネイティブのクロスプラット フォーム対応の .NET アプリの開発を開始するには、以下の手順に従って Visual Studio 2019 for Mac をインストールします。

 > [!div class="button"]
 > [Visual Studio for Mac をダウンロードする](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=navigation+cta&utm_content=download+vsmac2019)

## <a name="requirements"></a>必要条件

- macOS High Sierra 10.12 以降が搭載された Mac。

iOS または macOS 向けに Xamarin アプリをビルドするには、以下も必要になります。

- Xcode 10.0 以降。 通常は最新の安定バージョンをお勧めします。
- Apple ID。 Apple ID をまだ持っていない場合は、 https://appleid.apple.com で新しい ID を作成できます。 Xcode をインストールしてサインインするには、Apple ID を持っている必要があります。

## <a name="installation-instructions"></a>インストール手順

1. [Visual Studio for Mac のダウンロード ページ](https://aka.ms/vsmac)から、インストーラーをダウンロードします。
2. ダウンロードが完了したら、 **[VisualStudioforMacInstaller.dmg]** をクリックしてインストーラーをマウントし、矢印のロゴをダブルクリックして実行します。

    [![大きい矢印をクリックしてインストールを開始する](media/install-installer-sml.png)](media/install-installer.png#lightbox)

3. インターネットから、ダウンロードしているアプリケーションに関する警告が表示される場合があります。 **[開く]** をクリックします。
4. インストーラーがシステムを確認するまで待ちます。

    [![インストーラーがシステムにインストールされているコンポーネントを確認する](media/install-checking-sml.png)](media/install-checking.png#lightbox)

5. プライバシーとライセンス条項を確認するように求める警告が表示されます。 リンクに従ってそれらを読んでから、同意する場合は **[続行]** を押します。

    [![プライバシーと条項へのリンクに従って、同意する場合は続行する](media/install-privacy-sml.png)](media/install-privacy.png#lightbox)

6. 使用可能なワークロードの一覧が表示されます。 使用するコンポーネントを選択します。

    [![インストールしたいオプションのワークロード機能を選択する](media/install-selection.png)](media/install-selection.png#lightbox)

   すべてのプラットフォームをインストールすることを希望されない場合には、以下のガイドを使用してインストールするプラットフォームを決めることがきます。

   * **Xamarin を使用するアプリ**:
      - Xamarin.Forms – **Android** と **iOS** プラットフォームを選択します。
      - iOS のみ – **iOS** プラットフォームを選択します ([ **Xcode**](https://developer.apple.com/xcode/) をインストールする必要があります)。
      - Android のみ – **Android** プラットフォームを選択します (関連する依存関係も選択する必要があります)。
      - Mac のみ – **macOS** プラットフォームを選択します ([ **Xcode**](https://developer.apple.com/xcode/) をインストールする必要があります)。
      - 完全なクロスプラットフォームの Xamarin アプリ – **Android**、**iOS**、および**macOS** プラットフォームを選択します。
   * **.NET Core アプリケーション** – **.NET Core** プラットフォームを選択します。
   * **ASP.NET Core Web アプリケーション** – **.NET Core** プラットフォームを選択します。
   * **クロスプラットフォームの Unity ゲーム開発** – Visual Studio for Mac 以外の追加のプラットフォームをインストールする必要はありません。 Unity 拡張機能のインストールの詳細については、[Unity セットアップ ガイド](/visualstudio/mac/setup-vsmac-tools-unity)に関するページをご覧ください。

7. 選択を行ったら、 **[インストール]** ボタンを押します。
8. インストーラーではダウンロードの進行状況が表示され、Visual Studio for Mac と選択したワークロードがインストールされます。 インストールに必要な権限を付与するため、パスワードの入力が求められる場合があります。

企業環境でのインストール中にネットワークに問題が発生した場合は、[ファイアウォールまたはプロキシの背後へのインストール](https://docs.microsoft.com/visualstudio/mac/installation#install-visual-studio-for-mac-behind-a-firewall-or-proxy-server)の指示を確認してください。

[リリース ノート](https://docs.microsoft.com/visualstudio/releasenotes/vs2019-mac-relnotes)における変更点について学習します。

> [!NOTE]
> 元のインストールでプラットフォームやツールをインストールしなかった場合 (手順 6 でオフにした場合)、そのコンポーネントを後で追加するには、インストーラーをもう一度実行する必要があります。

## <a name="install-visual-studio-for-mac-behind-a-firewall-or-proxy-server"></a>ファイアウォールまたはプロキシ サーバーの内側に Visual Studio for Mac をインストールする

ファイアウォールの内側に Visual Studio for Mac をインストールするには、ソフトウェアに必要なツールと更新プログラムのダウンロードができるように特定のエンドポイントにアクセスできる必要があります。

以下の場所にアクセスできるようにネットワークを構成します。

- [Visual Studio エンドポイント](/visualstudio/install/install-visual-studio-behind-a-firewall-or-proxy-server)

## <a name="next-steps"></a>次の手順

Visual Studio for Mac をインストールすると、アプリのコードの記述を開始できます。 以下のガイドで、次の手順であるプロジェクトの記述と配置について説明します。

### <a name="ios"></a>iOS

1. [Hello, iOS](https://developer.xamarin.com/guides/ios/getting_started/hello,_iOS/)
2. [デバイス プロビジョニング](https://developer.xamarin.com/guides/ios/getting_started/installation/device_provisioning) (デバイスでアプリケーションを実行する場合)。

### <a name="android"></a>Android

1. [Xamarin Android SDK Manager の使用](https://developer.xamarin.com/guides/android/getting_started/installation/android-sdk/?ide=xs)
2. [Android SDK エミュレーター](https://developer.xamarin.com/guides/android/getting_started/installation/android-emulator/)
4. [開発用のデバイスの設定](https://developer.xamarin.com/guides/android/getting_started/installation/set_up_device_for_development/)

### <a name="net-core-apps-aspnet-core-web-apps-unity-game-development"></a>.NET Core アプリ, ASP.NET Core Web アプリ, Unity ゲーム開発

他のワークロードについては、[ワークロード](workloads.md)に関するページをご覧ください。

## <a name="related-video"></a>関連ビデオ

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Acquisition/player]

## <a name="see-also"></a>関連項目

- [Visual Studio のインストール (Windows)](/visualstudio/install/install-visual-studio)
