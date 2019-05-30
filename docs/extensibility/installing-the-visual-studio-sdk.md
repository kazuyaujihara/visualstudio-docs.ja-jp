---
title: Visual Studio SDK のインストール |Microsoft Docs
ms.date: 07/12/2018
ms.topic: conceptual
ms.assetid: c730edb6-5099-4c16-85a8-08def09f1455
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4208c20cc3e7da34efaf98af16f0f41d54613824
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66340756"
---
# <a name="install-the-visual-studio-sdk"></a>Visual Studio SDK のインストール

Visual Studio SDK (ソフトウェア開発キット) は、Visual Studio セットアップで省略可能な機能です。 また、後から VS SDK をインストールすることもできます。

## <a name="install-the-visual-studio-sdk-as-part-of-a-visual-studio-installation"></a>Visual Studio のインストールの一部として、Visual Studio SDK をインストールします。

VS SDK を Visual Studio のインストールに含めるには、ワークロードタブの**その他のツールセット**の下にある**Visual Studio 拡張機能の開発**ワークロードをインストールします。 このワークロードは、Visual Studio SDK と必要な前提条件をインストールします。 **インストールの詳細**ビューから、コンポーネントをオンまたはオフすることによって、インストールをさらにチューニングできます。

## <a name="install-the-visual-studio-sdk-after-installing-visual-studio"></a>Visual Studio をインストールした後で、Visual Studio SDK をインストールする

Visual Studio のインストールが完了した後、Visual Studio SDK をインストールするには、Visual Studio インストーラーを再実行し、**Visual Studio 拡張機能の開発**ワークロードを選択します。

## <a name="install-the-visual-studio-sdk-from-a-solution"></a>ソリューションから Visual Studio SDK をインストールします。

先にVS SDK をインストールせずに拡張機能プロジェクトを含むソリューションを開いた場合には、**Visual Studio 拡張機能の開発**ワークロードをインストールするための**見つからない機能のインストール**ダイアログが表示されます。

![拡張機能の開発をインストール](../extensibility/media/install-extension-development.png "拡張機能の開発のインストール")

## <a name="install-the-visual-studio-sdk-from-the-command-line"></a>コマンドラインから Visual Studio SDK をインストールする

ように、Visual Studio のワークロードやコンポーネントをインストールすることも、 **Visual Studio 拡張機能の開発**ワークロード (ID:Microsoft.VisualStudio.Workload.VisualStudioExtension) コマンドラインから。 適切なコマンド ライン スイッチとワークロードまたはコンポーネントの識別子を特定する方法についての一般的な手順の詳細については **[コマンド ライン パラメーターを使用して、Visual Studio をインストールする](../install/use-command-line-parameters-to-install-visual-studio.md)** を参照してください。

インストールされているVisual Studio のバージョンに一致する Visual Studio インストーラーを使用する必要があることに注意してください。 たとえば、Visual Studio Enterprise がコンピューターにインストールしてある場合は、Visual Studio Enterprise インストーラー(*vs_enterprise.exe*)を実行する必要があります 。