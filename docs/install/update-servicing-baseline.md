---
title: サービス ベースライン使用時の Visual Studio の更新
titleSuffix: ''
description: サービス ベースライン使用時の Visual Studio の更新方法について学習します。
ms.date: 05/22/2019
ms.custom: seodec18
ms.topic: conceptual
ms.assetid: ''
author: doughall
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 8928feffed77f8bfbb3787bd9a20737b9c7b3f9e
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66213783"
---
# <a name="update-visual-studio-while-on-a-servicing-baseline"></a>サービス ベースライン使用時の Visual Studio の更新

Visual Studio 2019 は、その[製品ライフサイクル](/visualstudio/productinfo/release-rhythm.md#release-channel-updates)中に頻繁に更新されます。 これらには、次の両方が含まれます: マイナー リリースの更新 (例:16.0 から 16.1) (新機能やコンポーネントが含まれることがあります) と、サービス更新 (例:16.0.4 から 16.0.5) (重要な問題のターゲット修正プログラムのみが含まれます) です。 

エンタープライズ管理者は、各自のクライアントがサービス ベースラインを使い続けるようにすることを選択できます。これにより、次のサービス ベースラインのリリースから 1 年間のサービス更新がサポートされます。 これによって、開発者と管理者が、新機能、バグの修正、または新しいマイナー更新に含まれるコンポーネントを、より柔軟に採用できるようになります。 最初のサービス ベースラインは 16.0.x です。 詳細については、「[Enterprise および Professional のお客様向けのサポート オプション](/visualstudio/releases/2019/servicing.md#support-options-for-enterprise-and-professional-customers)」をご覧ください。

## <a name="how-to-get-onto-a-servicing-baseline"></a>サービス ベースラインの使用を始める方法

サービス ベースラインの使用を開始するには、[My.VisualStudio.com](https://my.visualstudio.com/Downloads?q=visual%20studio%202019%20version%2016.0) から修正済みバージョンの Visual Studio インストーラーのブートストラップをダウンロードします。 これらのブートストラップには、その特定のバージョンの製品の構成、ワークロード、およびコンポーネントへのリンクが含まれています。 

> [!NOTE]
> 修正済みバージョンのブートストラップと通常のブートストラップを区別するよう注意してください。 通常のブートストラップは、入手可能な最新リリースの Visual Studio を使うよう構成されています。 my.visualstudio.com からダウンロードすると、そのファイル名に番号が記載されています (例: vs_enterprise__123456789-123456789.exe)。

インストール中に、エンタープライズ管理者は、クライアントが最新リリースに更新できないように構成する必要があります。 これを行うには、[応答構成ファイルで channelUri 設定を変更](update-servicing-baseline.md#install-a-servicing-baseline-on-a-network)してレイアウトまたはローカル フォルダー内のチャネル マニフェストを使うか、[コマンド ラインでの実行を使って channelUri を変更](update-servicing-baseline.md#install-a-servicing-baseline-via-the-internet)して存在しないファイルを使うか、または、[更新を無効にするようクライアント システム上のポリシーを設定](update-servicing-baseline.md#use-policy-settings-to-disable-clients-from-updating)してクライアントが自己更新できないようにします。 

### <a name="install-a-servicing-baseline-on-a-network"></a>ネットワーク上のサービス ベースラインをインストールする

ネットワーク レイアウト インストールを使う管理者の場合、レイアウトの `response.json` の channelUri 値を変更して、同じフォルダー内にある channelmanifest.json を使うようにします。 ステップ バイ ステップ ガイダンスについては、「[ネットワーク ベースの Visual Studio 配置の更新プログラムを制御する](controlling-updates-to-visual-studio-deployments.md)」をご覧ください。 channelUri を変更すると、クライアントがレイアウトの場所で更新プログラムを検索できるようになります。 

### <a name="install-a-servicing-baseline-via-the-internet"></a>インターネット経由でサービス ベースラインをインストールする

インターネット ベースのインストールを行う場合は、セットアップを起動するために使うコマンドラインに、`--channelUri` と存在しないチャンネル マニフェストを追加します。 これにより、Visual Studio の更新で入手可能な最新リリースを使えないようになります。 次に例を示します。

  ```cmd
   vs_enterprise.exe --channelUri c:\doesnotexist.chman 
  ```

### <a name="use-policy-settings-to-disable-clients-from-updating"></a>ポリシーの設定を使ってクライアントが更新できないようにする

クライアントの更新を制御するもう一つのオプションは、[更新通知をオフにする](controlling-updates-to-visual-studio-deployments.md)ことです。 インストールで channelUri 値が変更されていなかった場合は、このオプションを使います。 これで、クライアントが入手可能な最新リリースへのリンクを受信できなくなります。 修正済みバージョンのブートストラップは、クライアントで特定のバージョンに更新するために引き続き必要です。

## <a name="how-to-stay-on-a-servicing-baseline"></a>サービス ベースラインを使い続ける方法

サービス ベースライン用の更新プログラムがある場合、[My.VisualStudio.com](https://my.visualstudio.com/Downloads?q=visual%20studio%202019%20version%2016.0) からサービス更新用に修正済みバージョンのブートストラップ ファイルを入手できます。 これらはいくつかのシナリオで使用されます。

ネットワーク レイアウト インストールを介して配置する管理者の場合、管理者は[レイアウトの場所](update-a-network-installation-of-visual-studio.md)を更新する必要があります。 その場所からインストールしたクライアントは、更新通知を受け取ります。 更新プログラムをクライアントに配置する必要がある場合は、[こちらの手順](update-a-network-installation-of-visual-studio.md#how-to-deploy-an-update-to-client-machines)に従ってください。 更新用に 'response.json' を変更する場合は、追加のワークロード、コンポーネント、または言語を追加しないでください。 製品を更新した後は、このような設定の管理は配置の '変更' として実行する必要があります。 

インターネット ベースのインストールの場合は、新しい修正済みバージョンのブートストラップを、クライアント上の存在しないチャネル マニフェストを指す `--channelUri` パラメーターと共に実行します。 Quiet または受動モードで更新プログラムを配置する場合は、2 つの別々のコマンドを使います。

1. 最初に、Visual Studio インストーラーを更新します。 <br>```vs_enterprise.exe --quiet --update```
2. 次に、Visual Studio アプリケーション自体を更新します。 <br>```vs_enterprise.exe update --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise" --quiet --wait --norestart --channelUri c:\doesnotexist.chman```

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>関連項目

* [Visual Studio のインストール](install-visual-studio.md)
* [Visual Studio 管理者ガイド](visual-studio-administrator-guide.md)
* [コマンド ライン パラメーターを使用して Visual Studio をインストールする](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio インスタンスの検出および管理用のツール](tools-for-managing-visual-studio-instances.md)
* [応答ファイルの設定を定義する方法](automated-installation-with-response-file.md)
* [ネットワーク ベースの Visual Studio 配置の更新プログラムを制御する](controlling-updates-to-visual-studio-deployments.md)
* [Visual Studio の製品ライフサイクルとサービス](/visualstudio/releases/2019/servicing/)
