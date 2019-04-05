---
title: カスタム プロジェクト テンプレートと項目テンプレートの作成
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: 586da5dc-f678-402b-afd0-0332959fd7a6
caps.latest.revision: 11
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2e04ca6afaa8e5a290e6c2a3419bb4fa28fd46e6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58976332"
---
# <a name="creating-custom-project-and-item-templates"></a>カスタム プロジェクト テンプレートと項目テンプレートの作成
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio SDK には、カスタム プロジェクト テンプレートとカスタム項目テンプレートを作成するプロジェクト テンプレートが含まれています。 これらのテンプレートは、いくつかの一般的なパラメーター置換を含めるし、zip ファイルとしてビルドします。 自動的に展開されていないとは、実験用インスタンスで使用できません。 Zip ファイルをコピー先ファイル

テンプレートの作成テンプレートを使用してより大きな拡張機能でテンプレートを追加できます。 拡張機能でテンプレートを含めのソース ファイルにバージョン管理を実装し、1 つの VSIX パッケージ プロジェクト テンプレートのグループを作成することができます。

基本的なテンプレートの作成シナリオで使用する必要があります、**テンプレートのエクスポート**ウィザードで、圧縮されたファイルに出力します。 基本的なテンプレートの作成の詳細については、次を参照してください。[を作成するプロジェクトと項目テンプレート](../ide/creating-project-and-item-templates.md)します。

Visual Studio 2017 以降、カスタム プロジェクトと項目テンプレートをスキャンできなく実行されます。 代わりに、拡張機能では、これらのテンプレートのインストール場所を記述するテンプレート マニフェスト ファイルを提供する必要があります。 Preview 2 のインストールを使用するには、VSIX 拡張機能を更新します。 MSI を使用して、拡張機能をデプロイする場合は、手動でテンプレート マニフェスト ファイルを生成する必要があります。 詳細については、次を参照してください。[カスタム プロジェクトのアップグレードと Visual Studio 2017 の項目テンプレート](/visualstudio/extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017?view=vs-2015)します。 テンプレート マニフェスト スキーマについては[Visual Studio テンプレート マニフェスト スキーマ参照](/visualstudio/extensibility/visual-studio-template-manifest-schema-reference)します。

## <a name="create-a-project-template"></a>プロジェクト テンプレートを作成します。

1.  プロジェクト テンプレート プロジェクトを作成します。 プロジェクト テンプレートを見つけることができます、**新しいプロジェクト**ダイアログで、Visual Basic または Visual c# で**Extensibility**フォルダー。

     テンプレートは、クラス ファイル、アイコン、.vstemplate ファイル、ProjectTemplate.vbproj または ProjectTemplate.csproj、という名前を編集可能なプロジェクト ファイル、およびその他のプロジェクトの種類、このような resources.resx ファイル、AssemblyInfo によって通常生成されるいくつかのファイルが生成されます。ファイル、および .settings ファイル。 各コード ファイルには、適切な場所の一般的なパラメーターの代用が含まれています。

2.  追加し、プロジェクトの必要に応じてプロジェクトから項目を削除します。 編集可能なプロジェクト ファイル、AssemblyInfo ファイル、または、.vstemplate ファイルを削除しないでください。

3.  任意の追加と削除を反映するように、.vstemplate ファイルを更新します。 [プロジェクト](../extensibility/project-element-visual-studio-templates.md)要素を含める必要があります、 [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md)テンプレートに含まれる各ファイルの要素。

4.  コード ファイルとその他のユーザーに表示されるコンテンツを変更し、適切なパラメーター置換を追加します。

5.  必要に応じて生成されるコンテンツを変更します。

6.  プロジェクトをビルドします。

     Visual Studio では、テンプレートを含む .zip ファイルを作成します。 展開されていないと、実験用インスタンスで使用できなくなります。

## <a name="create-an-item-template"></a>項目テンプレートを作成します。

1.  項目テンプレート プロジェクトを作成します。

     テンプレートには、クラス ファイル、アイコン、.vstemplate ファイル、および、AssemblyInfo ファイルが生成されます。 クラス ファイルには、いくつかの一般的なパラメーターの代替文字列が含まれています。

2.  追加し、プロジェクトの必要に応じてプロジェクトから項目を削除します。

3.  任意の追加と削除を反映するように、.vstemplate ファイルを更新します。 [プロジェクト](../extensibility/project-element-visual-studio-templates.md)要素を含める必要があります、 [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md)テンプレートに含まれる各ファイルの要素。

4.  コード ファイルとその他のユーザーに表示されるコンテンツを変更し、適切なパラメーター置換を追加します。

5.  必要に応じて生成されるコンテンツを変更します。

6.  プロジェクトをビルドします。

     Visual Studio には、テンプレートを含む圧縮ファイルが作成されます。 展開されていないと、実験用インスタンスで使用できなくなります。

## <a name="deploy-the-project-or-item-template"></a>プロジェクトまたは項目テンプレートをデプロイします。

1.  VSIX プロジェクトを作成する。 詳細については、次を参照してください。 [VSIX プロジェクト テンプレート](../extensibility/vsix-project-template.md)します。

2.  VSIX プロジェクトをスタートアップ プロジェクトとして設定します。 **ソリューション エクスプ ローラー**、選択、VSIX プロジェクト ノードを右クリックし、**スタートアップ プロジェクトとして設定**します。

3.  VSIX プロジェクトの資産として、プロジェクト テンプレート プロジェクトを設定します。 .Vsixmanifest ファイルを開きます。 移動して、**資産** タブでをクリックし、**新規**します。

    1.  設定、**型**フィールドを**Microsoft.VisualStudio.ProjectTemplate**または **[microsoft.visualstudio.itemtemplate]** します。

    2.  ソースの選択、**現在のソリューションでプロジェクトを**オプション、およびテンプレートが含まれているプロジェクトを選択します。

4.  ソリューションをビルドし、F5 キーを押します。 実験用インスタンスが表示されます。

5.  プロジェクト テンプレート プロジェクトの場合に、記載されて、プロジェクト テンプレートを表示する必要があります、**新しいプロジェクト**ダイアログ (**ファイル/新しいプロジェクト/**)、Visual c# または Visual Basic ノード。 項目テンプレート プロジェクトでは、新しい項目の追加] ダイアログで、項目テンプレートが表示されます (で、**ソリューション エクスプ ローラー**プロジェクト ノードを選択して、クリックして**追加/[新しい項目の**)。

## <a name="see-also"></a>関連項目

- [Visual Studio テンプレート参照](../ide/visual-studio-template-reference.md)