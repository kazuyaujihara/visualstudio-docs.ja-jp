---
title: プロキシ認証が要求される | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: troubleshooting
ms.assetid: c2d24ae1-9902-460e-b72a-0299eed9ee82
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 520c31f671aee05663a5471aca05cfe06313b168
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65847030"
---
# <a name="proxy-authorization-required"></a>プロキシ認証が要求される
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

**プロキシ認証が要求**プロキシ サーバー経由の Visual Studio online リソースに接続されているユーザーとプロキシ サーバーが呼び出しをブロックするときに通常、エラーが発生します。

このエラーを修正するには、次の手順の 1 つ以上を試してください。

- Visual Studio を再起動します。 プロキシ認証のダイアログ ボックスが表示されます。 ダイアログ ボックスに資格情報を入力します。

- 上記の手順で問題が解決しない場合、考えられる原因は、プロキシ サーバーが http://go.microsoft.com のアドレスに対しては資格情報を要求せず、*.visualStudio.com のアドレスに対しては資格情報を要求することです。 これらのサーバーでは、Visual Studio ですべてのサインイン シナリオのブロックを解除する許可リストに、次の Url を追加する必要があります。

    - *.windows.net

    - *.microsoftonline.com

    - *.visualstudio.com

    - *.microsoftonline.com

    - *.live.com

- 削除することができます、[http://go.microsoft.com](http://go.microsoft.com ) アドレスを許可一覧から、プロキシ認証ダイアログ ボックスが両方に表示されるように、[http://go.microsoft.com](http://go.microsoft.com ) アドレスと Visual Studio を再起動すると、サーバー エンドポイント。

- プロキシで既定の資格情報を使用する場合は、次の操作を行います。

   1. devenv.exe.config (devenv.exe の構成ファイル) を次の場所から探します。 **%ProgramFiles%\Microsoft Visual Studio 14.0\Common7\IDE** (または **%ProgramFiles(x86)%\Microsoft Visual Studio 14.0\Common7\IDE**)

   2. 構成ファイル内で、 `<system.net>` ブロックを探し、次のコードを追加します。

      ```xml
      <defaultProxy enabled="true" useDefaultCredentials="true">
          <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>
      </defaultProxy>
      ```

      ネットワークの適切なプロキシ アドレスを挿入`proxyaddress="<http://<yourproxy:port#>`します。

- 指示に従って、[このブログの投稿](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx)プロキシを使用できるようにコードを追加します。
