---
title: '手順 1: Windows フォーム アプリケーション プロジェクトの作成'
ms.date: 03/23/2019
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 16ac2422-e720-4e3a-b511-bc2a54201a86
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7f529d737816406b3a4f6aa9921a8dc6b902d2fb
ms.sourcegitcommit: b14b7a938a2aba9fcce4d5e813aadf2040b0dcda
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58647363"
---
# <a name="step-1-create-a-windows-forms-application-project"></a>手順 1: Windows フォーム アプリケーション プロジェクトの作成

ピクチャ ビューアーを作成する場合、最初の手順は、Windows フォーム アプリケーション プロジェクトを作成することです。

 > [!TIP]
 > ![ビデオへのリンク](../data-tools/media/playvideo.gif)このトピックのビデオ版については、「[Tutorial 1:Create a picture viewer in Visual Basic - Video 1](http://go.microsoft.com/fwlink/?LinkId=205209)」(チュートリアル 1: Visual Basic でピクチャ ビューアーを作成する - ビデオ 1) または「[Tutorial 1:Create a picture viewer in C# - Video 1](http://go.microsoft.com/fwlink/?LinkId=205199)」(チュートリアル 1: C# でピクチャ ビューアーを作成する - ビデオ 1) をご覧ください。 これらのビデオでは、旧バージョンの Visual Studio を使用しているため、一部のメニュー コマンドやその他のユーザー インターフェイス要素が若干異なります。 ただし、概念および手順は、現在のバージョンの Visual Studio でも同様です。

::: moniker range="vs-2017"

## <a name="open-visual-studio-2017"></a>Visual Studio 2017 を開きます

1. メニュー バーで、**[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** を選択します。 ダイアログ ボックスは次のようになります。

     ![[新しいプロジェクト] ダイアログ ボックス](../ide/media/newprojectdialogcallouts.png)<br/>
***[新しいプロジェクト]** ダイアログ ボックス*

2. **[新しいプロジェクト]** ダイアログ ボックスの左側で、**[Visual C#]** または **[Visual Basic]** のいずれかを選択します。

3. テンプレート リストで、**[Windows フォーム アプリケーション (.NET Framework)]** を選択します。 新しいフォームに「**PictureViewer**」という名前を付け、**[OK]** をクリックします。

    >[!NOTE]
    >**[Windows フォーム アプリケーション (.NET Framework)]** テンプレートが表示されない場合は、Visual Studio インストーラーを使用して **[.NET デスクトップ開発]** ワークロードをインストールします。<br/><br/>![Visual Studio インストーラーでの [.NET デスクトップ開発] ワークロード](../ide/media/dot-net-desktop-dev-workload.png)<br/><br/> 詳細については、「[Visual Studio のインストール](../install/install-visual-studio.md)」を参照してください。

::: moniker-end

::: moniker range="vs-2019"

## <a name="open-visual-studio-2019"></a>Visual Studio 2019 を開く

1. スタート ウィンドウで、**[新しいプロジェクトの作成]** を選択します。

   ![[新しいプロジェクトの作成] ウィンドウを表示する](../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. **[新しいプロジェクトの作成]** ウィンドウで、検索ボックスに「*Windows フォーム*」と入力またはタイプします。 次に、言語のリストから **[Visual Basic]** を選択して、プラットフォームのリストから **[Windows]** を選択します。 

   言語およびプラットフォームのフィルターを適用してから、**[Windows フォーム アプリ (.NET Framework)]** テンプレートを選択し、**[次へ]** を選択します。

   ![Windows フォーム アプリ (.NET Framework) 用の Visual Basic テンプレートを選択する](../get-started/visual-basic/media/vs-2019/vb-create-new-project-search-winforms-filtered.png)

   > [!NOTE]
   > **[Windows フォーム アプリ (.NET Framework)]** テンプレートが表示されない場合は、**[新しいプロジェクトの作成]** ウィンドウからそれをインストールすることができます。 **[お探しの情報が見つかりませんでしたか?]** メッセージで、**[さらにツールと機能をインストールする]** リンクを選択します。
   >
   > ![[新しいプロジェクトの作成] ウィンドウに表示された [お探しの情報が見つかりませんでしたか?] での [さらにツールと機能をインストールする] リンク](../get-started/media/vs-2019/not-finding-what-looking-for.png) 
   > 
   > 次に、Visual Studio インストーラーで、**[.NET デスクトップの開発]** ワークロードを選択します。
   > 
   > ![Visual Studio インストーラーの .NET Core ワークロード](../ide/media/install-dot-net-desktop-env.png)
   >
   > その後、Visual Studio インストーラー内の **[変更]** ボタンをクリックします。 作業内容を保存するよう求められることがあります。その場合は、そのようにします。 次に、**[続行]** を選択してワークロードをインストールします。 

1. **[新しいプロジェクトの構成]** ウィンドウで、**[プロジェクト名]** ボックスに「*PictureViewer*」とタイプまたは入力します。 次に、**[作成]** を選択します。

::: moniker-end

Visual Studio はプログラムのソリューションを作成します。 ソリューションは、プログラムに必要なすべてのプロジェクトとファイルのコンテナーとして機能します。 これらについては、このチュートリアルで後ほど詳しく説明します。

## <a name="about-the-windows-forms-application-project"></a>Windows フォーム アプリケーション プロジェクトについて

1. 開発環境には、3 つのウィンドウ (メイン ウィンドウ、**ソリューション エクスプローラー**、**[プロパティ]** ウィンドウ) があります。

     これらのウィンドウのいずれかが表示されていない場合は、メニュー バーで **[ウィンドウ]** > **[ウィンドウ レイアウトのリセット]** の順に選択して、既定のウィンドウ レイアウトを復元します。 メニュー コマンドを使用してウィンドウを表示することもできます。 メニュー バーで、**[表示]** > **[プロパティ ウィンドウ]** または **[ソリューション エクスプローラー]** の順に選択します。 他のウィンドウが開いている場合は、右上隅の **[閉じる]** (x) ボタンを選択して閉じます。

    ::: moniker range="vs-2017"

    - **メイン ウィンドウ** このウィンドウでは、フォームの操作やコードの編集など、ほとんどの作業を行います。 このウィンドウに、**フォーム エディター**のフォームが表示されています。 ウィンドウの上部には、**[スタート ページ]** タブと **[Form1.cs [デザイン]]** タブが表示されています  (Visual Basic では、タブの名前は *.cs* ではなく *.vb* で終わります)。

    ::: moniker-end

    ::: moniker range=">=vs-2019"

    - **メイン ウィンドウ** このウィンドウでは、フォームの操作やコードの編集など、ほとんどの作業を行います。 このウィンドウに、**フォーム エディター**のフォームが表示されています。

    ::: moniker-end

    - **ソリューション エクスプローラーウィンドウ** このウィンドウでは、ソリューション内のすべての項目を確認し、各項目に移動できます。 ファイルを選択すると、**[プロパティ]** ウィンドウの内容が変わります。 コード ファイル (Visual C# の場合は *.cs*、Visual Basic の場合は *.vb* で終わるファイル) を開くと、コード ファイルまたはコード ファイルのデザイナーが表示されます。 デザイナーは、ボタンやリストなどのコントロールを追加できるビジュアル サーフェイスです。 Visual Studio のフォームでは、デザイナーは **Windows フォーム デザイナー**と呼ばれます。

    - **[プロパティ] ウィンドウ** このウィンドウでは、他のウィンドウで選択した項目のプロパティを変更できます。 たとえば、Form1 を選択した場合、**Text** プロパティを設定してタイトルを変更し、**Backcolor** プロパティを設定して背景色を変更することができます。

    > [!NOTE]
    > **ソリューション エクスプローラー**の先頭行には、"**ソリューション 'PictureViewer' (1 プロジェクト)**" と表示されています。これは、Visual Studio によってソリューションが作成されたことを意味します。 ソリューションには複数のプロジェクトを含めることができますが、ここでは、プロジェクトを 1 つだけ含むソリューションを使用します。

1. メニュー バーで、**[ファイル]** > **[すべてを保存]** の順に選択します。

     または、次の図に示すツール バーの **[すべて保存]** ボタンを選択します。

     ![[すべてを保存] ツール バー ボタン](../ide/media/express_iconsaveall.png)<br/>
     ***[すべてを保存]** ツール バー ボタン*

     Visual Studio によって自動的にフォルダー名およびプロジェクト名が指定され、projects フォルダーにプロジェクトが保存されます。

## <a name="to-continue-or-review"></a>続行または確認するには

- チュートリアルの次の手順に進むには、「[手順 2:プログラムを実行する](../ide/step-2-run-your-program.md)」を参照してください。

- 概要のトピックに戻るには、「[チュートリアル 1: ピクチャ ビューアーの作成](../ide/tutorial-1-create-a-picture-viewer.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [新しい Windows フォームの作成](/dotnet/framework/winforms/creating-a-new-windows-form/)