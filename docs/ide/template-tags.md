---
title: プロジェクト テンプレート上でタグを追加または編集する
ms.date: 04/30/2019
author: minsa110
ms.author: somin
manager: jillfra
ms.topic: reference
helpviewer_keywords:
- item templates, updating
- Visual Studio templates, updating
- project templates, updating
- updating templates [Visual Studio]
- template tagging, updating
- template tags, updating
ms.openlocfilehash: 4a5113fa7f420d58892e2737ec9196422486490e
ms.sourcegitcommit: cd21b38eefdea2cdefb53e68e7a30b868e78dd6b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2019
ms.locfileid: "66038628"
---
# <a name="add-tags-to-project-templates"></a>プロジェクト テンプレートにタグを追加する

[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/) バージョン 16.1 Preview 2 以降では、言語、プラットフォーム、プロジェクト タイプのタグを自分のプロジェクト テンプレートに追加できます。 タグは、新しいプロジェクト ダイアログ ボックスの 2 つの場所で使用されます。

- テンプレートの説明の下にタグが表示されます

   ![新しいプロジェクト ダイアログでのタグを含むプロジェクト テンプレート](media/npd-item-with-template-tags.png)

- タグを使って、テンプレートを検索およびフィルター処理できます

   ![新しいプロジェクト ダイアログでの検索とフィルター処理](media/npd-search-and-filter.png)

Visual Studio に組み込まれているテンプレート タグを使って *.vstemplate* XML ファイルを更新するか、カスタム テンプレート タグを作成することで、タグを追加できます。 テンプレート タグは、Visual Studio 2019 の新しいプロジェクト ダイアログでのみ使えます。 それらは、以前のバージョンの Visual Studio でのテンプレートのレンダリングには影響がありません。

## <a name="add-or-edit-tags"></a>タグを追加または編集する

次を行う場合、プロジェクト テンプレートの *.vstemplate* XML でタグを追加または編集できます。

* [テンプレートのエクスポート] ウィザードを使って[新しいプロジェクト テンプレートを作成する](/visualstudio/ide/how-to-create-project-templates)

* [既存のプロジェクト テンプレートを更新する](/visualstudio/ide/how-to-update-existing-templates)

* [新しい VSIX プロジェクト テンプレートを作成する](/visualstudio/extensibility/getting-started-with-the-vsix-project-template)

## <a name="syntax"></a>構文

```xml
<LanguageTag> Language Name </LanguageTag>
<PlatformTag> Platform Name </PlatformTag>
<ProjectTypeTag> Project Type </ProjectTypeTag>
```

## <a name="attributes"></a>属性

次の属性は省略可能であり、高度なユーザー シナリオ用です。

|属性|説明|
|---------------|-----------------|
|`Package`|Visual Studio のパッケージ ID を指定する GUID です。|
|`ID`|Visual Studio のリソース ID を指定します。|

構文:

```xml
<LanguageTag Package="{PackageID}" ID="ResourceID" />
<PlatformTag Package="{PackageID}" ID="ResourceID" />
<ProjectTypeTag Package="{PackageID}" ID="ResourceID" />
```

## <a name="elements"></a>Elements

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|(必須) テンプレートをカテゴリに分類し、 **[新しいプロジェクト]** または **[新しい項目の追加]** ダイアログ ボックスでそれがどのように表示されるかを定義します。|

## <a name="text-value"></a>テキスト値

`Package` と `ID` 属性を使わない限り、テキスト値が必要です。

テキストによってテンプレートの名前を指定します。

## <a name="built-in-tags"></a>組み込みのタグ

Visual Studio では一連の組み込みタグが提供されています。これらを追加すると、ローカライズされたリソースをレンダリングできます。 組み込みのタグと、それらに対応するかっこで囲まれた値の一覧を次に示します。

| 言語 | プラットフォーム | プロジェクトの種類 |
| -- | -- | -- |
| C++ (`cpp`) | Android (`android`) | クラウド (`cloud`) |
| C# (`csharp`) | Azure (`azure`) | コンソール (`console`) |
| F# (`fsharp`) | iOS (`ios`) | デスクトップ (`desktop`) |
| Java (`java`) | Linux (`linux`) | 拡張機能 (`extension`) |
| JavaScript (`javascript`) | macOS (`macos`) | ゲーム (`games`) |
| Python (`python`) | tvOS (`tvos`) | IoT (`iot`) |
| クエリ言語 (`querylanguage`) | Windows (`windows`) | ライブラリ (`library`) |
| TypeScript (`typescript`) | Xbox (`xbox`) | 機械学習 (`machinelearning`) |
| Visual Basic (`visualbasic`) | | モバイル (`mobile`) |
| | | Office (`office`) |
| | | その他 (`other`) |
| | | サービス (`service`) |
| | | テスト (`test`) |
| | | UWP (`uwp`) |
| | | Web (`web`) |

## <a name="example"></a>例

Visual C# アプリケーションでのプロジェクト テンプレートのメタデータの例を次に示します。

```xml
<VSTemplate Type="Project" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>My template</Name>
        <Description>A basic template</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <LanguageTag>C#</LanguageTag>
        <PlatformTag>windows</PlatformTag>
        <PlatformTag>linux</PlatformTag>
        <PlatformTag>My Platform</PlatformTag>
        <ProjectTypeTag>console</ProjectTypeTag>
        <ProjectTypeTag>desktop</ProjectTypeTag>
    </TemplateData>
    <TemplateContent>
        <Project File="MyTemplate.csproj">
            <ProjectItem>Form1.cs<ProjectItem>
            <ProjectItem>Form1.Designer.cs</ProjectItem>
            <ProjectItem>Program.cs</ProjectItem>
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>
            <ProjectItem>Properties\Resources.resx</ProjectItem>
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>
            <ProjectItem>Properties\Settings.settings</ProjectItem>
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>関連項目

- [Visual Studio テンプレート スキーマ参照](/visualstudio/extensibility/visual-studio-template-schema-reference)
- [プロジェクトと項目テンプレートの作成](/visualstudio/ide/creating-project-and-item-templates)
- [プロジェクト テンプレートと項目テンプレートのカスタマイズ](/visualstudio/ide/customizing-project-and-item-templates)
- [VSIX プロジェクトのテンプレートの概要](/visualstudio/extensibility/getting-started-with-the-vsix-project-template)