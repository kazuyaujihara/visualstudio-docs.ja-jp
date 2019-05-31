---
title: VSIX プロジェクト テンプレートの概要 |Microsoft Docs
ms.date: 3/16/2019
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio SDK, VSIX project template
ms.assetid: 89fac33e-9380-4723-9b45-048a6e16f0ed
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a8bb85e507e62bf7dd13288cbd08d7bf9d06973e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66342459"
---
# <a name="get-started-with-the-vsix-project-template"></a>VSIX プロジェクト テンプレートを概要します。

拡張機能を作成するか、パッケージの展開の既存の拡張機能は、VSIX プロジェクト テンプレートを使用できます。 VSIX プロジェクト テンプレートは、Visual Basic と Visual c# の両方のバージョンを備え、Visual Studio SDK の一部としてインストールされます。

 VSIX プロジェクト テンプレートは構成だけを*source.extension.vsixmanifest*ファイルで、出荷、拡張機能と、資産に関する情報が含まれます。

 VSIX プロジェクト テンプレートを検索するには、Visual Studio SDK をインストールする必要があります。 詳細については、次を参照してください。 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)します。

## <a name="deploy-a-custom-project-template-using-the-vsix-project-template"></a>VSIX プロジェクト テンプレートを使用してカスタム プロジェクト テンプレートのデプロイします。

 次の手順では、VSIX プロジェクトを使用して、他の開発者と共有または Visual Studio ギャラリーにアップロードできるプロジェクト テンプレートをパッケージ化する方法を示します。

1. プロジェクト テンプレートを作成します。

    1. テンプレートを作成するためのプロジェクトを開きます。 このプロジェクトは、あらゆる種類のプロジェクトのできます。

    2. **[プロジェクト]** メニューの **[テンプレートのエクスポート]** をクリックします。 ウィザードの手順を実行します。

         A *.zip*にファイルが作成 *%USERPROFILE%\My documents \visual Studio {バージョン} \My エクスポートされたテンプレート\\* します。

2. 空の VSIX プロジェクトを作成します。

     **[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** を順に選択します。 検索ボックスで、"vsix"を入力し、いずれかを選択、 **C#** または**Visual Basic**版**VSIX プロジェクト**します。

3. 追加、 *.zip*ファイルをプロジェクトにします。 設定の**出力ディレクトリにコピー**プロパティを`Copy Always`します。

4. **ソリューション エクスプ ローラー**、ダブルクリックして、 *source.extension.vsixmanifest*で開くファイルを**VSIX マニフェスト デザイナー**、し、次の変更。

    - 設定、**製品名**フィールドを**マイ プロジェクト テンプレート**します。

    - 設定、**製品 ID**フィールドを**MyProjectTemplate - 1**します。

    - 設定、**作成者**フィールドを**Fabrikam**します。

    - 設定、**説明**フィールドを**プロジェクト テンプレート**します。

    - **資産**セクションで、追加、 **Microsoft.VisualStudio.ProjectTemplate**を入力し、そのパスの名前に設定、 *.zip*ファイル。

5. 保存して閉じます、 *source.extension.vsixmanifest*ファイル。

6. プロジェクトをビルドします。

7. 出力ディレクトリをダブルクリック、 *.vsix*ファイル。

8. A **VSIX インストーラー**メッセージ ボックスが表示されます。 拡張機能をインストールする手順に従います。

9. Visual Studio をいったん閉じて開きなおします。

::: moniker range="vs-2017"

10. 選択**拡張機能と更新**(上、**ツール**メニュー) を選択し、**テンプレート**カテゴリ。 使用可能な拡張機能のいずれかにする必要があります**マイ プロジェクト テンプレート**します。

::: moniker-end

::: moniker range=">=vs-2019"

10. 選択**拡張機能の管理**(上、**拡張機能**メニュー) を選択し、**テンプレート**カテゴリ。 使用可能な拡張機能のいずれかにする必要があります**マイ プロジェクト テンプレート**します。

::: moniker-end

11. 新しいプロジェクト テンプレートに表示される、**新しいプロジェクト**元のプロジェクト テンプレートと同じ場所にダイアログ。 たとえば、という名前のテンプレートを作成した**VB コンソール**から Visual Basic コンソール アプリケーションでは、 **VB コンソール**Visual Basic と同じペインが表示されます**のコンソールアプリケーション**テンプレート。

### <a name="to-specify-the-location-of-the-template-in-the-new-project-dialog-box"></a>新しいプロジェクト ダイアログ ボックスで、テンプレートの場所を指定するには

1. テンプレート フォルダーにある、 *{Visual Studio インストール パス} \Common7\IDE\ProjectTemplates*と *{Visual Studio インストール パス} \Common7\IDE\ItemTemplates*ディレクトリ。 最上位レベルのセクションでは、名前、**新しいプロジェクト**ダイアログは、テンプレート フォルダーの名前と一致しません。 これらが異なる場合は、テンプレート フォルダーの名前を使用します。

    変更、 *.vsix*ファイルに拡張子 *.zip*、し、ファイルを開きます。

2. セクションと同じ名前の新しいフォルダーを作成、**新しいプロジェクト**ダイアログにテンプレートが表示する必要があります。

3. テンプレートのサブセクションに表示される場合、同じ名前のサブフォルダーを作成します。

4. テンプレートを移動 *.zip*新しいフォルダにファイル。

5. 変更、 *.zip*拡張機能を *.vsix*します。

6. VSIX マニフェストを開きます。

7. VSIX マニフェストでは、更新、**資産**ことは、テンプレート ファイルを格納するディレクトリ ツリーのルートを指すためのテンプレートのパス。 たとえば、次のテンプレートが *\CSharp\Windows*、参照が指す必要があります *\CSharp*します。
