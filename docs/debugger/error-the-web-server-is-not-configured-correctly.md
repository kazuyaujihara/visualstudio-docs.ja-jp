---
title: 'エラー: web サーバーが正しく構成されていません |Microsoft Docs'
ms.date: 09/20/2017
ms.topic: troubleshooting
f1_keywords:
- vs.debug.remote.projnotconfigured
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: be5db0a08a287e2611c29396e96e72719b5106a7
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72736926"
---
# <a name="error-the-web-server-is-not-configured-correctly"></a>エラー : Web サーバーは正しく構成されていません。

ここで説明する手順を実行して問題を解決した後、デバッグを再試行する前に、IIS のリセットが必要になる場合もあります。 これを行うには、管理者のコマンドプロンプトを開き、「`iisreset`」と入力します。

この問題を解決するには、次の手順を実行します。

1. サーバーでホストされている web アプリがリリースビルドとして構成されている場合は、デバッグビルドとして再発行し、web.config ファイルにコンパイル要素の `debug=true` が含まれていることを確認します。 IIS をリセットして、再試行してください。

    たとえば、リリースビルドに発行プロファイルを使用している場合は、それを [デバッグ] に変更して再発行します。 そうしないと、発行時に debug 属性が `false` に設定されます。

2. インターネット物理パスが正しいことを確認してください。 IIS では、この設定は [**基本設定 > 物理パス**(または以前のバージョンの IIS の**詳細設定**)] で確認できます。

    Web アプリケーションが別のコンピューターにコピーされた場合、手動で名前を変更した場合、または移動した場合は、物理パスが正しくない可能性があります。 IIS をリセットして、再試行してください。

3. Visual Studio でローカルにデバッグしている場合は、プロパティで正しいサーバーが選択されていることを確認します。 ([**プロパティ] > [Web > サーバー**またはプロパティ] を開いて、プロジェクトの種類に応じて**デバッグ >** ます。 Web フォームプロジェクトの場合は、**プロパティページ > 開始オプション > サーバー**) を開きます。

    IIS などの外部 (カスタム) サーバーを使用している場合は、URL が正しいことが必要です。 それ以外の場合は、[IIS Express] を選択して再試行します。

4. インターネット正しいバージョンの ASP.NET がサーバーにインストールされていることを確認してください。

    IIS と Visual Studio プロジェクトで ASP.NET のバージョンが一致しないと、この問題が発生する可能性があります。 場合によっては、web.config でフレームワークのバージョンを設定する必要があります。IIS に ASP.NET をインストールするには、 [Web Platform Installer (WebPI)](https://www.microsoft.com/web/downloads/platform.aspx)を使用します。 また、 [ASP.NET 3.5 と ASP.NET 4.5 を使用した iis 8.0](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) 、ASP.NET Core の場合は[iis を使用した Windows でのホスト](https://docs.asp.net/en/latest/publishing/iis.html)を参照してください。

4. IIS の `maxConnection` 制限が低すぎて、接続が多すぎる場合は、[接続数の上限を引き上げる](/iis/configuration/system.applicationhost/sites/sitedefaults/limits)必要があります。

## <a name="see-also"></a>関連項目
- [リモートの IIS コンピューター上の ASP.NET のリモート デバッグ](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)
- [Web アプリケーションのデバッグ : エラーおよびトラブルシューティング](../debugger/debugging-web-applications-errors-and-troubleshooting.md)