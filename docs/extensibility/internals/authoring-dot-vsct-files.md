---
title: 文書.Vsct ファイル |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, manual authoring
ms.assetid: e9f715dc-12b7-439b-bdf3-f3dc75e62f1c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 82960de02c43a7c4002e189d573a914bb2a73f20
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73186655"
---
# <a name="author-vsct-files"></a>作成した vsct ファイル
このドキュメントでは、メニュー項目、ツールバー、およびその他のユーザーインターフェイス (UI) 要素を Visual Studio 統合開発環境 (IDE) に追加するために、vsct ファイルを作成する方法について説明*します*。 この手順は、まだ*vsct*ファイルがない Visual Studio パッケージ (VSPackage) に UI 要素を追加する場合に使用します。

 新しいプロジェクトでは、Visual Studio パッケージテンプレートを使用することをお勧めし*ます。* これは、選択内容によっては、メニューコマンド、ツールウィンドウ、またはカスタムエディターに必要な要素が既に存在するためです。 この*vsct*ファイルを変更して、VSPackage の要件を満たすことができます。 *Vsct*ファイルを変更する方法の詳細については、「[メニューとコマンドの拡張](../../extensibility/extending-menus-and-commands.md)」の例を参照してください。

## <a name="author-the-file"></a>ファイルを作成する
 これらのフェーズで*vsct*ファイルを作成します。ファイルとリソースの構造を作成し、ui 要素を宣言し、ui 要素を IDE に配置し、特殊な動作を追加します。

### <a name="file-structure"></a>ファイル構造
 *Vsct*ファイルの基本構造は[commandtable](../../extensibility/commandtable-element.md)ルート要素であり、 [Commands](../../extensibility/commands-element.md)要素と[Symbols](../../extensibility/symbols-element.md)要素が含まれています。

#### <a name="to-create-the-file-structure"></a>ファイル構造を作成するには

1. [「方法: vsct ファイルを作成](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)する」の手順に従って、 *vsct*ファイルをプロジェクトに追加します。

2. 次の例に示すように、必要な名前空間を `CommandTable` 要素に追加します。

    ```xml
    <CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable"
        xmlns:xs="http://www.w3.org/2001/XMLSchema">

    ```

3. `CommandTable` 要素に、すべてのカスタムメニュー、ツールバー、コマンドグループ、およびコマンドをホストするための `Commands` 要素を追加します。 カスタム UI 要素が読み込まれるようにするには、`Commands` 要素の `Package` 属性がパッケージの名前に設定されている必要があります。

     `Commands` 要素の後に、パッケージの Guid、および UI 要素の名前とコマンド Id を定義する `Symbols` 要素を追加します。

### <a name="include-visual-studio-resources"></a>Visual Studio リソースを含める
 [Extern](../../extensibility/extern-element.md)要素を使用して、Visual Studio のコマンドを定義するファイルと、IDE に UI 要素を配置するために必要なメニューをアクセスします。 パッケージの外部で定義されているコマンドを使用する場合は、使用する[コマンド](../../extensibility/usedcommands-element.md)要素を使用して Visual Studio に通知します。

#### <a name="to-include-visual-studio-resources"></a>Visual Studio リソースを含めるには

1. `CommandTable` 要素の先頭に、参照する外部ファイルごとに1つの `Extern` 要素を追加し、`href` 属性をファイルの名前に設定します。 次のヘッダーファイルを参照して、Visual Studio リソースにアクセスできます。

   - *Stdidcmd*: Visual Studio によって公開されるすべてのコマンドの id を定義します。

   - *Vsshlids. h*: Visual Studio メニューのコマンド id が含まれています。

2. パッケージが Visual Studio または他のパッケージで定義されているコマンドを呼び出す場合は、`Commands` 要素の後に `UsedCommands` 要素を追加します。 この要素には、パッケージの一部ではない、呼び出すコマンドごとに使用される[command](../../extensibility/usedcommand-element.md)要素を設定します。 `UsedCommand` 要素の `guid` 属性と `id` 属性を、呼び出すコマンドの GUID と ID の値に設定します。

   Visual Studio コマンドの Guid と Id を検索する方法の詳細については、「 [Visual studio コマンドの guid と id](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)」を参照してください。 他のパッケージからコマンドを呼び出すには、そのパッケージの*vsct*ファイルで定義されているように、GUID とコマンドの ID を使用します。

### <a name="declare-ui-elements"></a>UI 要素の宣言
 *Vsct*ファイルの `Symbols` セクションで、すべての新しい UI 要素を宣言します。

#### <a name="to-declare-ui-elements"></a>UI 要素を宣言するには

1. `Symbols` 要素で、3つの[Guidsymbol](../../extensibility/guidsymbol-element.md)要素を追加します。 各 `GuidSymbol` 要素には、`name` 属性と `value` 属性があります。 要素の目的を反映するように `name` 属性を設定します。 `value` 属性は GUID を受け取ります。 (GUID を生成するには、 **[ツール]** メニューの **[guid の作成]** を選択し、 **[レジストリ形式]** を選択します)。

     最初の `GuidSymbol` 要素は、パッケージを表します。通常、子はありません。 2番目の `GuidSymbol` 要素は、コマンドセットを表します。この要素には、メニュー、グループ、およびコマンドを定義するすべての記号が含まれます。 3番目の `GuidSymbol` 要素はイメージストアを表し、コマンドのすべてのアイコンのシンボルが含まれています。 アイコンを使用するコマンドがない場合は、3番目の `GuidSymbol` 要素を省略できます。

2. コマンドセットを表す `GuidSymbol` 要素で、1つまたは複数の[Idsymbol](../../extensibility/idsymbol-element.md)要素を追加します。 これらはそれぞれ、UI に追加するメニュー、ツールバー、グループ、またはコマンドを表します。

     各 `IDSymbol` 要素について、`name` 属性を、対応するメニュー、グループ、またはコマンドを参照するために使用する名前に設定し、`value` 要素をそのコマンド ID を表す16進数に設定します。 同じ親を持つ2つの `IDSymbol` 要素の値を同じにすることはできません。

3. UI 要素のいずれかにアイコンが必要な場合は、各アイコンの `IDSymbol` 要素を、イメージストアを表す `GuidSymbol` 要素に追加します。

### <a name="put-ui-elements-in-the-ide"></a>UI 要素を IDE に配置する
 [メニュー](../../extensibility/menus-element.md)、[グループ](../../extensibility/groups-element.md)、および[ボタン](../../extensibility/buttons-element.md)の各要素には、パッケージで定義されているすべてのメニュー、グループ、およびコマンドの定義が含まれています。 これらのメニュー、グループ、およびコマンドは、UI 要素定義の一部である[親](../../extensibility/parent-element.md)要素を使用するか、別の場所で定義された[commandplacement](../../extensibility/commandplacement-element.md)要素を使用して、IDE に配置します。

 各 `Menu`、`Group`、および `Button` 要素には、`guid` 属性と `id` 属性があります。 `guid` 属性は、常に、コマンドセットを表す `GuidSymbol` 要素の名前と一致するように設定し、`id` 属性を、`Symbols` セクションのメニュー、グループ、またはコマンドを表す `IDSymbol` 要素の名前に設定します。

#### <a name="to-define-ui-elements"></a>UI 要素を定義するには

1. 新しいメニュー、サブメニュー、ショートカットメニュー、またはツールバーを定義する場合は、`Commands` 要素に `Menus` 要素を追加します。 次に、作成するメニューごとに、[メニュー](../../extensibility/menu-element.md)要素を `Menus` 要素に追加します。

    `Menu` 要素の `guid` と `id` 属性を設定し、`type` 属性を目的のメニューの種類に設定します。 また、`priority` 属性を設定して、親グループ内のメニューの相対位置を設定することもできます。

   > [!NOTE]
   > `priority` 属性は、ツールバーやコンテキストメニューには適用されません。

2. Visual Studio IDE のすべてのコマンドは、メニューとツールバーの直接の子であるコマンドグループでホストされている必要があります。 新しいメニューやツールバーを IDE に追加する場合は、新しいコマンドグループが含まれている必要があります。 コマンドを視覚的にグループ化できるように、既存のメニューやツールバーにコマンドグループを追加することもできます。

    新しいコマンドグループを追加する場合は、最初に `Groups` 要素を作成してから、各コマンドグループの[group](../../extensibility/group-element.md)要素を追加する必要があります。

    各 `Group` 要素の `guid` と `id` 属性を設定し、`priority` 属性を設定して、親メニューのグループの相対位置を設定します。 詳細については、「[再利用可能なボタンのグループの作成](../../extensibility/creating-reusable-groups-of-buttons.md)」を参照してください。

3. IDE に新しいコマンドを追加する場合は、`Commands` 要素に `Buttons` 要素を追加します。 次に、各コマンドに対して、`Buttons` 要素に[Button](../../extensibility/button-element.md)要素を追加します。

   1. 各 `Button` 要素の `guid` と `id` 属性を設定し、`type` 属性を必要なボタンの種類に設定します。 また、`priority` 属性を設定して、親グループ内のコマンドの相対位置を確立することもできます。

       > [!NOTE]
       > ツールバーの標準のメニューコマンドとボタンには `type="button"` を使用します。

   2. `Button` 要素で、 [Buttontext](../../extensibility/buttontext-element.md)要素と[CommandName](../../extensibility/commandname-element.md)要素を含む[Strings](../../extensibility/strings-element.md)要素を追加します。 `ButtonText` 要素は、メニュー項目のテキストラベル、またはツールバーボタンのツールヒントを提供します。 `CommandName` 要素には、コマンドウェルで使用するコマンドの名前を指定します。

   3. コマンドにアイコンが表示される場合は、`Button` 要素に[icon](../../extensibility/icon-element.md)要素を作成し、その `guid` 属性と `id` 属性をアイコンの `Bitmap` 要素に設定します。

       > [!NOTE]
       > ツールバーのボタンにはアイコンが必要です。

   詳細については、「 [Menucommands と OleMenuCommands](/visualstudio/extensibility/menucommands-vs-olemenucommands?view=vs-2015)」を参照してください。

4. いずれかのコマンドでアイコンが必要な場合は、`Commands` 要素に[ビットマップ](../../extensibility/bitmaps-element.md)要素を追加します。 次に、各アイコンに対して、`Bitmaps` 要素に[Bitmap](../../extensibility/bitmap-element.md)要素を追加します。 ここで、ビットマップリソースの場所を指定します。 詳細については、「[メニューコマンドにアイコンを追加する](../../extensibility/adding-icons-to-menu-commands.md)」を参照してください。

   ほとんどのメニュー、グループ、およびコマンドを正しく配置するには、親構造に依存することができます。 非常に大きなコマンドセットの場合、またはメニュー、グループ、またはコマンドを複数の場所に表示する必要がある場合は、コマンドの配置を指定することをお勧めします。

#### <a name="to-rely-on-parenting-to-place-ui-elements-in-the-ide"></a>親を使用して IDE に UI 要素を配置するには

1. 一般的な親として、パッケージに定義されている各 `Menu`、`Group`、および `Command` 要素に `Parent` 要素を作成します。

    `Parent` 要素のターゲットは、メニュー、グループ、またはコマンドを格納するグループです。

   1. `guid` 属性を、コマンドセットを定義する `GuidSymbol` 要素の名前に設定します。 ターゲット要素がパッケージに含まれていない場合は、対応する*vsct*ファイルで定義されているように、そのコマンドセットの guid を使用します。

   2. `id` 属性を、ターゲットメニューまたはグループの `id` 属性と一致するように設定します。 Visual Studio によって公開されているメニューとグループの一覧については、「visual [studio メニューの guid と id](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md) 」、または「 [visual studio のツールバーの guid と id](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)」を参照してください。

   IDE に配置する UI 要素が多数ある場合、または複数の場所に出現する要素がある場合は、次の手順に示すように、それらの配置を[commandplacements](../../extensibility/commandplacements-element.md)要素に定義します。

#### <a name="to-use-command-placement-to-place-ui-elements-in-the-ide"></a>コマンドの配置を使用して UI 要素を IDE に配置するには

1. `Commands` 要素の後に、`CommandPlacements` 要素を追加します。

2. `CommandPlacements` 要素で、配置するメニュー、グループ、またはコマンドごとに `CommandPlacement` 要素を追加します。

    各 `CommandPlacement` 要素または `Parent` 要素は、1つの IDE の場所に1つのメニュー、グループ、またはコマンドを配置します。 UI 要素は親を1つだけ持つことができますが、複数のコマンドを配置することができます。 UI 要素を複数の場所に配置するには、場所ごとに `CommandPlacement` 要素を追加します。

3. `Parent` 要素の場合と同様に、各 `CommandPlacement` 要素の `guid` 属性と `id` 属性を、ホストするメニューまたはグループに設定します。 また、`priority` 属性を設定して、UI 要素の相対位置を設定することもできます。

   配置とコマンドの配置を組み合わせることができます。 ただし、非常に大きなコマンドセットの場合は、コマンドの配置のみを使用することをお勧めします。

### <a name="add-specialized-behaviors"></a>特殊な動作の追加
 [Commandflag](../../extensibility/command-flag-element.md)要素を使用して、メニューやコマンドの外観や表示を変更するなどの動作を変更できます。 [VisibilityConstraints](../../extensibility/visibilityconstraints-element.md)要素を使用してコマンドが表示されるタイミングに影響を与えることも、キー[バインド](../../extensibility/keybindings-element.md)要素を使用してキーボードショートカットを追加することもできます。 特定の種類のメニューとコマンドには、既に特殊な動作が組み込まれています。

#### <a name="to-add-specialized-behaviors"></a>特殊な動作を追加するには

1. 特定の UI コンテキストでのみ UI 要素を表示するようにするには (たとえば、ソリューションが読み込まれるとき)、可視性の制約を使用します。

   1. `Commands` 要素の後に、`VisibilityConstraints` 要素を追加します。

   2. 制約する各 UI 項目に対して、 [VisibilityItem](../../extensibility/visibilityitem-element.md)要素を追加します。

   3. `VisibilityItem` 要素ごとに、`guid` 属性と `id` 属性をメニュー、グループ、またはコマンドに設定し、<xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> クラスで定義されているように、`context` 属性を目的の UI コンテキストに設定します。

2. コード内の UI 項目の可視性または可用性を設定するには、次のコマンドフラグの1つまたは複数を使用します。

   - `DefaultDisabled`

   - `DefaultInvisible`

   - `DynamicItemStart`

   - `DynamicVisibility`

   - `NoShowOnMenuController`

   - `NotInTBList`

   詳細については、「 [Commandflag](../../extensibility/command-flag-element.md)要素」を参照してください。

3. 要素の表示方法を変更したり、要素の外観を動的に変更したりするには、次のコマンドフラグの1つまたは複数を使用します。

   - `AlwaysCreate`

   - `CommandWellOnly`

   - `DefaultDocked`

   - `DontCache`

   - `DynamicItemStart`

   - `FixMenuController`

   - `IconAndText`

   - `Pict`

   - `StretchHorizontally`

   - `TextMenuUseButton`

   - `TextChanges`

   - `TextOnly`

   詳細については、「 [Commandflag](../../extensibility/command-flag-element.md)要素」を参照してください。

4. コマンドを受信したときの要素の反応を変更するには、次のコマンドフラグの1つまたは複数を使用します。

   - `AllowParams`

   - `CaseSensitive`

   - `CommandWellOnly`

   - `FilterKeys`

   - `NoAutoComplete`

   - `NoButtonCustomize`

   - `NoKeyCustomize`

   - `NoToolbarClose`

   - `PostExec`

   - `RouteToDocs`

   - `TextIsAnchorCommand`

   詳細については、「 [Commandflag](../../extensibility/command-flag-element.md)要素」を参照してください。

5. メニューまたはメニュー項目にメニュー依存のキーボードショートカットをアタッチするには、メニューまたはメニュー項目の `ButtonText` 要素にアンパサンド文字 (&) を追加します。 アンパサンドの後に続く文字は、親メニューが開いているときのアクティブなキーボードショートカットです。

6. メニューに依存しないショートカットキーをコマンドにアタッチするには、キー[バインド](../../extensibility/keybindings-element.md)要素を使用します。 詳細については、「[キーバインド](../../extensibility/keybinding-element.md)要素」を参照してください。

7. メニューテキストをローカライズするには、`LocCanonicalName` 要素を使用します。 詳細については、「 [Strings](../../extensibility/strings-element.md) 」要素を参照してください。

   メニューとボタンの種類には、特殊な動作があります。 次の一覧では、いくつかの特殊なメニューとボタンの種類について説明します。 その他の型については、[メニュー](../../extensibility/menu-element.md)、[ボタン](../../extensibility/button-element.md)、および[コンボ](../../extensibility/combo-element.md)要素の `types` 属性の説明を参照してください。

   - コンボボックス: コンボボックスは、ツールバーで使用できるドロップダウンリストです。 UI にコンボボックスを追加するには、`Commands` 要素に[Combos](../../extensibility/combos-element.md)要素を作成します。 次に、追加する各コンボボックスの `Combo` 要素を `Combos` 要素に追加します。 `Combo` 要素は、`Button` 要素と同じ属性および子を持ち、`DefaultWidth` 属性と `idCommandList` 属性も持っています。 `DefaultWidth` 属性はピクセル単位の幅を設定し、`idCommandList` 属性はコンボボックスの設定に使用されるコマンド ID を指します。

   - メニューコントローラー: メニューコントローラーは、その横に矢印が付いたボタンです。 矢印をクリックすると、一覧が表示されます。 メニューコントローラーを UI に追加するには、`Menu` 要素を作成し、必要な動作に応じて、その `type` 属性を `MenuController` または `MenuControllerLatched`に設定します。 メニューコントローラーを設定するには、`Group` 要素の親として設定します。 メニューコントローラーには、そのグループのすべての子がドロップダウンリストに表示されます。

## <a name="see-also"></a>関連項目
- [メニューとコマンドを拡張する](../../extensibility/extending-menus-and-commands.md)
- [Visual Studio コマンドテーブル (vsct) ファイル](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [VSCT XML スキーマリファレンス](../../extensibility/vsct-xml-schema-reference.md)