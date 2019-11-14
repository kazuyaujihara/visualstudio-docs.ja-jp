---
title: 実行中の ASP.NET process を検索する |Microsoft Docs
ms.date: 11/04/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- ASP.NET debugging, ASP.NET process
- ASP.NET process
ms.assetid: 931a7597-b0f0-4a28-931d-46e63344435f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
ms.openlocfilehash: 54aa98dd238d7a78e4ae89af05dceae0f9911478
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73187660"
---
# <a name="find-the-name-of-the-aspnet-process"></a>ASP.NET プロセスの名前を見つける

実行中の [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] アプリをデバッグするには、Visual Studio デバッガーを名前で [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] プロセスにアタッチする必要があります。

**ASP.NET アプリを実行しているプロセスを確認するには、次の手順を実行します。**

1. アプリを実行している状態で、Visual Studio で **デバッグ** > **プロセスにアタッチ** を選択します。

1. **[プロセスにアタッチ]** ダイアログボックスで、次の一覧にあるプロセス名の最初の文字を入力するか、検索ボックスに入力します。 実行されているものは、ASP.NET アプリを実行しているアプリケーションです。 アプリケーションをデバッグするには、そのプロセスにアタッチします。

    - w3wp.exe*は IIS 6.0 以降です。*
    - *aspnet_wp.exe*は、以前のバージョンの IIS です。
    - *iisexpress*は iisexpress です。
    - *dotnet*は ASP.NET Core です。
    - *inetinfo.exe*は、インプロセスで実行されている古い ASP アプリケーションです。

>[!NOTE]
>Visual Studio 2012 以前の [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] コードは、ファイルシステム上に配置し、テストサーバー *Webdev.* WebServer40 または*webdev. .exe*で実行できます。 この場合、ローカルデバッグの場合は、[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] プロセスではなく、WebServer40 または*Webdev. .exe*に*アタッチします*。

**関連項目:**

- [実行中のプロセスにアタッチする](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)
- [Web アプリケーションをリモートデバッグするための前提条件](remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)
- [システム要件](../debugger/aspnet-debugging-system-requirements.md)
- [ASP.NET アプリケーションをデバッグする](../debugger/how-to-enable-debugging-for-aspnet-applications.md)