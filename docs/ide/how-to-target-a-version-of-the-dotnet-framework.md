---
title: 対象とする .NET Framework のバージョン
ms.date: 03/21/2019
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- .NET Framework version [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ba8bdcade321c3660e89ab6b7cf6e0b79471b393
ms.sourcegitcommit: 3201da3499051768ab59f492699a9049cbc5c3c6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2019
ms.locfileid: "58355397"
---
# <a name="how-to-target-a-version-of-the-net-framework"></a>方法:.NET Framework のバージョンをターゲットにする

この記事では、プロジェクトを作成するときに、.NET Framework のバージョンをターゲットにする方法について説明します。 既存の Visual Basic、C#、または F# のプロジェクトでターゲットにされたバージョンを変更する方法についても説明します。

> [!IMPORTANT]
> C++ プロジェクトのターゲット バージョンを変更する方法については、「[方法:ターゲット フレームワークおよびプラットフォームのツールセットを変更する](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)」を参照してください。

## <a name="target-a-version-when-you-create-a-project"></a>プロジェクト作成時にバージョンをターゲットにする

プロジェクトを作成するときに使用できる .NET Framework のバージョンは、インストールされたバージョンと選択されたプロジェクト テンプレートによって変わります。

1. メニュー バーで、**[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** を選択します。

1. 作成するプロジェクトの種類のテンプレートを選択します。 プロジェクトの名前を入力します。

1. ダイアログ ボックスの下部にある **[Framework]** ドロップダウン リストから、プロジェクトでターゲットとする .NET Framework のバージョンを選択します。

   [Framework] リストには、選択したテンプレートに適用できるバージョンのみが表示されます。 .NET Core など、プロジェクトの種類によっては、.NET Framework が必要ありません。 このような場合、**[Framework]** ドロップダウン リストは非表示になります。

   ::: moniker range="vs-2017"

   ![[新しいプロジェクト] ダイアログ ボックスの [Framework] ドロップダウン リスト](media/vside-newproject-framework.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![VS 2019 での Framework セレクター](media/vs-2019/configure-new-project-framework.png)

   ::: moniker-end

1. [プロジェクトの作成](create-new-project.md)を続行します。

## <a name="change-the-targeted-version"></a>ターゲットとするバージョンを変更する

Visual Basic、C#、または F# のプロジェクトでターゲットとされている .NET Framework バージョンを変更するには、次の手順を行います。

1. **ソリューション エクスプローラー**で、変更するプロジェクトのショートカット メニューを開き、**[プロパティ]** を選択します。

    ![Visual Studio のソリューション エクスプローラーのプロパティ](../ide/media/vs_slnexplorer_properties.png)

1. **[プロパティ]** ウィンドウの左側の列で、**[アプリケーション]** タブを選択します。

    ![Visual Studio のアプリのプロパティの [アプリケーション] タブ](../ide/media/vs_slnexplorer_properties_applicationtab.png)

    > [!NOTE]
    > UWP アプリを作成した後は、Windows または .NET Framework のターゲット バージョンを変更することはできません。

1. **[ターゲット フレームワーク]** 一覧で、目的のバージョンを選択します。

1. 表示される検証ダイアログ ボックスで **[はい]** ボタンを選択します。

    プロジェクトがアンロードされます。 プロジェクトを再読み込みすると、上で選択した .NET Framework のバージョンが対象になります。

    > [!NOTE]
    > 対象とするバージョンとは別の .NET Framework のバージョンへの参照がコードに含まれている場合、コードをコンパイルまたは実行するとエラー メッセージが表示されることがあります。 これらのエラーを解決するには、参照を変更する必要があります。 「[.NET Framework を対象とするエラーのトラブルシューティング](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [Visual Studio のマルチ ターゲットの概要](../ide/visual-studio-multi-targeting-overview.md)
- [.NET Framework を対象とするエラーのトラブルシューティング](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)
- [[アプリケーション] ページ (プロジェクト デザイナー) (C#)](../ide/reference/application-page-project-designer-csharp.md)
- [[アプリケーション] ページ (プロジェクト デザイナー) (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)
- [方法: ターゲット フレームワークおよびプラットフォームのツールセットを変更する (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)