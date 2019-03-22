---
title: 拡張機能パック項目テンプレートを使用して、拡張機能パックを作成する |Microsoft Docs
ms.date: 07/27/2018
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - extensions
ms.assetid: 5388EEBA-211D-4114-8CD9-70C899919F7E
author: gregvanl
ms.author: gregvanl
manager: Meng
ms.workload:
- vssdk
ms.openlocfilehash: 7899a096bb2a56e93ea55a4ba0a17cde272bd615
ms.sourcegitcommit: 4d9c54f689416bf1dc4ace058919592482d02e36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58193706"
---
# <a name="walkthrough-create-an-extension-pack"></a>チュートリアル: 拡張機能パックを作成する

拡張機能パックには、一連の拡張機能を一緒にインストールすることができます。 拡張機能パックを使用すると、簡単にお気に入りの拡張機能を他のユーザーに共有または特定のシナリオの拡張機能のセットをバンドルできます。

## <a name="prerequisites"></a>必須コンポーネント

Visual Studio SDK は Visual Studio 2015 以降では Visual Studio のセットアップのオプション機能として含まれます。 また、後から VS SDK をインストールすることもできます。 より詳細な情報については 、[Visual Studio SDK のインストール](../extensibility/installing-the-visual-studio-sdk.md) に関する記事を参照してください。

拡張機能パックの機能は、Visual Studio 15.8 Preview 2 以降から使用できます。

## <a name="create-an-extension-with-an-extension-pack-item-template"></a>拡張機能を拡張パック項目テンプレートの作成します。

拡張機能パック項目テンプレートは、一緒にインストールすることができる拡張機能のセットを拡張機能パックを作成します。

1. **新しいプロジェクト**ダイアログ ボックスで、検索を選択して"vsix" **VSIX プロジェクト**します。 **プロジェクト名**、「テスト拡張機能パック」を入力します。 **[作成]** を選択します。

2. **ソリューション エクスプ ローラー**でプロジェクト ノードを右クリックし、選択**追加** > **新しい項目の**します。 移動する、Visual c#**拡張**ノード**拡張パック**します。 既定のファイル名 (ExtensionPack1.cs) のままにします。

3. 次のコードを含む、ExtensionPack1.vsext ファイルが追加されます。

   ```json
   {
    "id": "ExtensionPack1",
    "name": "ExtensionPack1",
    "description": "Read about creating extension packs at https://aka.ms/vsextpack",
    "version": "1.0.0.0",
    "extensions": [  // List of extensions that are included in the Extension Pack.
      {
        "vsixId": "41858b2d-ff0b-4a43-80b0-f1b2d6084935", // The vsix id of the extension you want to   include.
        "name": "AlignAssignments"
      },
      {
          "vsixId": "42374550-426a-400e-96f9-237682e8dea6",
        "name": "CopyAsHtml"
      }
    ]
   }
   ```

4. 拡張機能パックに含めない拡張機能の vsixid で確認できます、 [Visual Studio Marketplace](https://marketplace.visualstudio.com/)します。 拡張機能を含める をクリックする**コピー ID**します。 既存を更新する**vsixId**上記のファイルまたはリストに別の拡張機能を追加します。

    ![Marketplace から VsixId をコピーします。](media/vsixid-marketplace.png)

5. プロジェクトをビルドし、拡張機能を Marketplace にアップロードします。 参照してください[Visual Studio 拡張機能を公開](../extensibility/walkthrough-publishing-a-visual-studio-extension.md)します。

> [!NOTE]
> 拡張機能パックをで使用できる拡張機能をインストールのみ、 [Visual Studio Marketplace](https://marketplace.visualstudio.com/)または[プライベート ギャラリー](../extensibility/how-to-create-an-atom-feed-for-a-private-gallery.md)します。

## <a name="install-the-extension-pack-from-the-visual-studio-marketplace"></a>Visual Studio Marketplace から拡張機能パックをインストールします。

これで、拡張機能を公開すると、Visual Studio にインストールし、テストします。

::: moniker range="vs-2017"

1. Visual Studio での**ツール** メニューのをクリックして**拡張機能と更新**します。

::: moniker-end

::: moniker range=">=vs-2019"

1. Visual Studio での**拡張** メニューのをクリックして**マネージ拡張**。

::: moniker-end

2. クリックして**オンライン**し、「テスト拡張機能パック」を検索します。

3. **[ダウンロード]** をクリックします。 拡張機能と拡張機能パックに含まれる拡張機能のリストは、インストールのスケジュールされます。

4. 以下のサンプル拡張機能パック ダウンロード ビューには、**拡張機能の管理**ダイアログ。 拡張の一覧を変更するには、拡張機能パックに含まれる拡張機能の一部のみをインストールする場合は、**インストールのスケジュールされた**します。

    ![Marketplace から拡張機能パックをダウンロードします。](media/vside-extensionpack.png)

5. インストールを完了するには、Visual Studio のすべてのインスタンスを閉じます。

## <a name="remove-the-extension"></a>拡張機能を削除します。

コンピューターから、拡張機能を削除します。

::: moniker range="vs-2017"

1. Visual Studio での**ツール** メニューのをクリックして**拡張機能と更新**します。

::: moniker-end

::: moniker range=">=vs-2019"

1. Visual Studio での**拡張** メニューのをクリックして**マネージ拡張**。

::: moniker-end

2. 選択**テスト拡張パック** をクリックし、**アンインストール**します。 拡張機能と拡張機能パックに含まれる拡張機能のリストは、アンインストールのスケジュールされます。

3. アンインストールを完了するには、Visual Studio のすべてのインスタンスを閉じます。
