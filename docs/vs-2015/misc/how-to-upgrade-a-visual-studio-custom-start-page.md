---
title: '方法: カスタム スタート ページのアップグレード |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
ms.assetid: 78342ce6-36c8-485b-a5f6-760e7a420a26
caps.latest.revision: 8
manager: jillfra
ms.openlocfilehash: 4e17ed6ac15dbaee08c596b67a70b53f440a1e1e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "59002418"
---
# <a name="how-to-upgrade-a-visual-studio-custom-start-page"></a>方法: Visual Studio のカスタム スタート ページをアップグレードします。
次の手順に従って、Visual Studio 2010 または Visual Studio 2012 のカスタム スタート ページを Visual Studio 2015 にアップグレードできます。

> [!WARNING]
>  この手順でアップグレードするカスタム スタート ページは、Visual Studio ギャラリーの [カスタム スタート ページ](http://visualstudiogallery.msdn.microsoft.com/f655a5dc-1a2d-4eca-b774-76c352c03b87) テンプレートで作成されたページです。 スタート ページにアップグレードが必要なその他の機能がある場合があります。

### <a name="to-upgrade-a-custom-start-page-to-visual-studio-2015"></a>カスタム スタート ページを Visual Studio 2015 にアップグレードするには

1.  Visual Studio 2015 と Visual Studio 2015 SDK がインストールされていることを確認します。 [Microsoft Visual Studio 2013 SDK](https://my.visualstudio.com/Downloads?pid=1436)から VSSDK をダウンロードできます。

2.  カスタム テンプレート プロジェクトを開きます。 プロジェクトをアップグレードすることを通知するメッセージが表示されます。 **[OK]** をクリックしてアップグレードが完了するまで待機します。

3.  スタート ページ プロジェクトとコントロール プロジェクトの両方のプロジェクト プロパティで、ターゲット フレームワークが、少なくとも .NET Framework 4.5 であることを確認します。

4.  スタート ページ プロジェクトのプロジェクト プロパティの [デバッグ] カテゴリで、Visual Studio 2015 バージョンの devenv.exe へのパスを設定します。

5.  両方のプロジェクトのプロジェクト参照で、Microsoft.VisualStudio.Shell.11.0 への参照を削除し、Microsoft.VisualStudio.Shell.14.0 への参照を追加します。

6.  XML エディターで StartPage.xaml を開き、次の変更を行います。

    1.  名前空間を更新します。 次の行を

        ```

        xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.11.0"
         xmlns:vsfxim="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.Immutable.11.0"
        xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.11.0"
        ```

         次のように変更します。

        ```

        xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.142.0"
         xmlns:vsfxim="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.Immutable.14.0"
        xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"
        ```

7.  MyControl.xaml を開き、名前空間参照 `xmlns:vs="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.11.0"` を `xmlns:vs="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"` に変更します。