---
title: ツール ウィンドウで拡張機能の作成 |Microsoft Docs
ms.date: 3/16/2019
ms.topic: conceptual
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b5a38c9912be87c94c79076675b5db25663fb5f0
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345430"
---
# <a name="create-an-extension-with-a-tool-window"></a>ツール ウィンドウでの拡張機能を作成します。

この手順で、VSIX プロジェクト テンプレートを使用する方法について説明しますと、**カスタム ツール ウィンドウ**ツール ウィンドウで、拡張機能を作成する項目テンプレート。

## <a name="prerequisites"></a>必須コンポーネント

 Visual Studio 2015 以降、ダウンロード センターから Visual Studio SDK をインストールすることはできません。 これは Visual Studio のセットアップにオプション機能として含まれるようになりました。 また、後から VS SDK をインストールすることもできます。 詳細については、"[Visual Studio SDK をインストール](../extensibility/installing-the-visual-studio-sdk.md)"を参照してください。

### <a name="create-a-tool-window"></a>ツール ウィンドウを作成します。

1. という名前の VSIX プロジェクトを作成する**最初**します。 VSIX プロジェクト テンプレートを見つけることができます、**新しいプロジェクト**ダイアログで"vsix"を検索します。

2. という名前のツール ウィンドウの項目テンプレートを追加、プロジェクトが開いたら、 **MyWindow**します。 **ソリューション エクスプ ローラー**でプロジェクト ノードを右クリックし、選択**追加** > **新しい項目の**します。 **新しい項目の追加**ダイアログ ボックスに移動して**Visual c#**  > **拡張**選択と**カスタム ツール ウィンドウ**。 **名前**ウィンドウの下部にあるフィールドに、ツール ウィンドウのファイル名を変更して*MyWindow.cs*します。

3. プロジェクトをビルドし、デバッグを開始します。

   Visual Studio の実験用インスタンスが表示されます。 実験用インスタンスの詳細については、次を参照してください。[実験用インスタンス](../extensibility/the-experimental-instance.md)します。

4. 実験用のインスタンスに移動**ビュー** > **その他の Windows**します。

   メニュー項目を表示する必要があります**MyWindow**します。 クリックします。

   タイトルのツール ウィンドウが表示**MyWindow** 、ボタン台詞**ここです。**