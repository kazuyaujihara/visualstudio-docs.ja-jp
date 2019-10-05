---
title: Analyzer ルールの重要度と抑制
ms.date: 09/23/2019
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 3222509ccc5ec20cd1433d215ca3d69609af6bcb
ms.sourcegitcommit: 39a04f42d23597b70053686d7e927ba78f38a9a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2019
ms.locfileid: "71975022"
---
# <a name="use-code-analyzers"></a>コードアナライザーを使用する

.NET Compiler Platform ("Roslyn") コードアナライザーではC# 、入力に応じてコードまたは Visual Basic が分析されます。 各*診断*または規則には、プロジェクトで上書きできる既定の重大度と抑制状態があります。 この記事では、ルールの重要度の設定、ルールセットの使用、および違反の抑制について説明します。

## <a name="analyzers-in-solution-explorer"></a>ソリューションエクスプローラーのアナライザー

**ソリューションエクスプローラー**から、analyzer 診断のカスタマイズの多くを行うことができます。 アナライザーを NuGet パッケージとして[インストール](../code-quality/install-roslyn-analyzers.md)すると、**ソリューションエクスプローラー**の **[参照]** ノードまたは **[依存関係]** ノードの下に **[アナライザー]** ノードが表示されます。 [アナライザー] を展開して**から、いずれ**かのアナライザーアセンブリを展開すると、アセンブリ内のすべての診断が表示されます。

![ソリューションエクスプローラーのアナライザーノード](media/analyzers-expanded-in-solution-explorer.png)

**[プロパティ]** ウィンドウでは、診断のプロパティや既定の重要度などを表示できます。 プロパティを表示するには、ルールを右クリックして **[プロパティ]** を選択するか、ルールを選択して**Alt**+**enter**キーを押します。

![プロパティウィンドウの診断プロパティ](media/analyzer-diagnostic-properties.png)

診断のオンラインドキュメントを表示するには、診断を右クリックし、 **[ヘルプの表示]** を選択します。

**ソリューションエクスプローラー**の各診断の横にあるアイコンは、エディターで開いたときにルールセットに表示されるアイコンに対応します。

- 円の "x" は**エラー**の[重大度](#rule-severity)を示します。
- 三角形の "!" は**警告**の[重大度](#rule-severity)を示します。
- 円の "i" は**情報**の[重大度](#rule-severity)を示します。
- 明るい色の背景にある円の "i" は、**非表示**の[重要度](#rule-severity)を示します。
- 円の下向き矢印は、診断が抑制されていることを示します。

![ソリューションエクスプローラーの診断アイコン](media/diagnostics-icons-solution-explorer.png)

## <a name="rule-severity"></a>ルールの重要度

::: moniker range=">=vs-2019"

アナライザーを NuGet パッケージとして[インストール](../code-quality/install-roslyn-analyzers.md)した場合は、analyzer ルールまたは*診断*の重大度を構成できます。 Visual Studio 2019 バージョン16.3 以降では、 [EditorConfig ファイルで](#set-rule-severity-in-an-editorconfig-file)ルールの重要度を構成できます。 また、ソリューションエクスプローラーまたは[ルールセットファイル](#set-rule-severity-in-the-rule-set-file)[から](#set-rule-severity-from-solution-explorer)、ルールの重要度を変更することもできます。

::: moniker-end

::: moniker range="vs-2017"

アナライザーを NuGet パッケージとして[インストール](../code-quality/install-roslyn-analyzers.md)した場合は、analyzer ルールまたは*診断*の重大度を構成できます。 ルールの重要度は、ソリューションエクスプローラーまたは[ルールセットファイルの中](#set-rule-severity-in-the-rule-set-file)[から](#set-rule-severity-from-solution-explorer)変更できます。

::: moniker-end

次の表は、さまざまな重大度オプションを示しています。

| 重要度 (ソリューションエクスプローラー) | 重大度 (EditorConfig ファイル) | ビルド時の動作 | エディターの動作 |
|-|-|-|
| Error | `error` | エラー一覧とコマンドラインのビルド出力で、違反が*エラー*として表示され、ビルドが失敗します。| 問題のあるコードに赤い波線が表示され、スクロールバーに小さな赤色のボックスが付きます。 |
| 警告 | `warning` | エラー一覧とコマンドラインのビルド出力では、違反は*警告*として表示されますが、ビルドが失敗することはありません。 | 問題のあるコードには緑色の波線が表示され、スクロールバーには小さな緑色のボックスが付きます。 |
| Info | `suggestion` | 違反は、コマンドラインのビルド出力ではなく、エラー一覧に*メッセージ*として表示されます。 | 問題のあるコードは灰色の波で下線が引かれ、スクロールバーの小さな灰色のボックスによってマークされます。 |
| [非表示] | `silent` | ユーザーに表示されません。 | ユーザーに表示されません。 ただし、診断は IDE 診断エンジンに報告されます。 |
| なし | `none` | 完全に抑制されます。 | 完全に抑制されます。 |
| 既定 | `default` | ルールの既定の重要度に対応します。 ルールの既定値を確認するには、プロパティウィンドウを調べます。 | ルールの既定の重要度に対応します。 |

次のコードエディターのスクリーンショットは、重大度が異なる3種類の違反を示しています。 波線の色と、右側のスクロールバーの小さな色付きの正方形に注目してください。

![コードエディターのエラー、警告、および情報の違反](media/diagnostics-severity-colors.png)

次のスクリーンショットは、エラー一覧に表示されるのと同じ3つの違反を示しています。

![エラー一覧のエラー、警告、および情報の違反](media/diagnostics-severities-in-error-list.png)

::: moniker range=">=vs-2019"

### <a name="set-rule-severity-in-an-editorconfig-file"></a>EditorConfig ファイルで規則の重要度を設定する

(Visual Studio 2019 バージョン16.3 以降)

EditorConfig ファイルでルールの重要度を指定するための一般的な構文は次のとおりです。

`dotnet_diagnostic.<rule ID>.severity = <severity>`

EditorConfig ファイルでのルールの重要度の設定は、ルールセットまたはソリューションエクスプローラーで設定されている重要度よりも優先されます。 EditorConfig ファイルで重大度を[手動で](#manually-configure-rule-severity)構成することも、違反の隣に表示される電球を介して[自動的に](#automatically-configure-rule-severity)構成することもできます。

#### <a name="manually-configure-rule-severity"></a>規則の重要度を手動で構成する

1. プロジェクトの EditorConfig ファイルがまだない場合は、プロジェクトを[追加](../ide/create-portable-custom-editor-options.md#add-an-editorconfig-file-to-a-project)します。

2. 対応するファイル拡張子の下で、構成する各ルールのエントリを追加します。 たとえば、 [CA1822](ca1822-mark-members-as-static.md)の重大度をファイルのC# `error` に設定すると、エントリは次のようになります。

   ```ini
   [*.cs]
   dotnet_diagnostic.CA1822.severity = error
   ```

> [!NOTE]
> IDE コードスタイルのアナライザーでは、別の構文を使用して EditorConfig ファイルで構成することもできます (`dotnet_style_qualification_for_field = false:suggestion` など)。 ただし、`dotnet_diagnostic` 構文を使用して重要度を設定した場合は、それが優先されます。 詳細については、「 [EditorConfig の言語規則](../ide/editorconfig-language-conventions.md)」を参照してください。

#### <a name="automatically-configure-rule-severity"></a>規則の重要度を自動的に構成する

Visual Studio には、[クイックアクション](../ide/quick-actions.md)の電球メニューからルールの重要度を構成する便利な方法が用意されています。

1. 違反が発生した後、エディターで違反波線をポイントし、電球メニューを開きます。 または、行にカーソルを置き、 **ctrl**+ キーを押し**ます。** (ピリオド) を押します。

2. 電球メニューの **問題の構成または非**表示 を選択し > **\<rule ID > Severity** を構成します。

   ![Visual Studio の電球メニューからルールの重要度を構成する](media/configure-rule-severity.png)

3. そこから、重大度オプションの1つを選択します。

   ![規則の重要度を提案として構成する](media/configure-rule-severity-suggestion.png)

   Visual Studio によって EditorConfig ファイルにエントリが追加され、[プレビュー] ボックスに示されているように、要求されたレベルに規則が構成されます。

   > [!TIP]
   > プロジェクトに EditorConfig ファイルがまだない場合は、Visual Studio によって作成されます。

::: moniker-end

### <a name="set-rule-severity-from-solution-explorer"></a>ルールの重要度をソリューションエクスプローラーから設定

1. **ソリューションエクスプローラー**で、 **[参照]**  > **アナライザー** (**または**.Net Core プロジェクトの場合  > **アナライザー** ) を展開します。

1. 重要度を設定するルールが含まれているアセンブリを展開します。

1. ルールを右クリックし、 **[ルールセットの重要度の設定]** を選択します。 [] ボックスの [重要度] オプションの1つを選択します。

   ルールの重要度は、アクティブなルールセットファイルに保存されます。

### <a name="set-rule-severity-in-the-rule-set-file"></a>規則セットファイルで規則の重要度を設定する

![ソリューションエクスプローラーの規則セットファイル](media/ruleset-in-solution-explorer.png)

1. **ソリューションエクスプローラー**でアクティブな[ルールセット](analyzer-rule-sets.md)ファイルをダブルクリックして開き、 **[参照]**  > **アナライザー**ノードの右クリックメニューで **[アクティブなルールセットを開く]** を選択するか、または **[開く]** を選択します **。プロジェクトのコード分析**のプロパティページ。

   規則セットを初めて編集する場合は、Visual Studio によって既定の規則セットファイルのコピーが作成され、 *\< projectname >* という名前が付いてプロジェクトに追加されます。 このカスタム規則セットは、プロジェクトのアクティブな規則セットにもなります。

   > [!NOTE]
   > .NET Core と .NET Standard のプロジェクトでは、 **[アクティブな規則セットを開く]** など、**ソリューションエクスプローラー**の規則セットのメニューコマンドはサポートされていません。 .NET Core または .NET Standard プロジェクトに対して既定以外の規則セットを指定するには、 [ **CodeAnalysisRuleSet**プロパティ](using-rule-sets-to-group-code-analysis-rules.md#specify-a-rule-set-for-a-project)をプロジェクトファイルに手動で追加します。 ただし、Visual Studio の規則セットエディター UI で規則セット内の規則を構成することはできます。

1. コンテナーのアセンブリを展開して、規則を参照します。

1. **[アクション]** 列で、値を選択してドロップダウンリストを開き、一覧から目的の重要度を選択します。

   ![エディターでルールセットファイルを開く](media/ruleset-file-in-editor.png)

## <a name="suppress-violations"></a>違反を抑制する

規則違反を抑制する方法は複数あります。

::: moniker range=">=vs-2019"

- **Editorconfig ファイル**内

  重大度を `none` に設定します (たとえば、`dotnet_diagnostic.CA1822.severity = none`)。

- **[分析]** メニューから

  メニューバーの [@no__t の**分析**] を選択し**て**、現在のすべての違反を非表示にします。 これは、"基準" と呼ばれることもあります。

::: moniker-end

::: moniker range="vs-2017"

- **[分析]** メニューから

  [**分析**@no__t] を選択し、メニューバーの [**コード分析の実行] と [アクティブな問題の非**表示] をクリックして、現在のすべての違反を抑制します。 これは、"基準" と呼ばれることもあります。

::: moniker-end

- **ソリューションエクスプローラー**から

  規則の重要度を **[なし**] に設定します。

- **規則セットエディター**から

  名前の横にあるボックスをオフにするか、 **[アクション]** を **[なし**] に設定します。

- **コードエディター**から

  違反があるコード行にカーソルを置き、 **Ctrl**+**ピリオド (.)** キーを押して、 **[クイックアクション]** メニューを開きます。 [**ソース/抑制ファイルの** **caxxxx** > ] を選択します。

  ![クイックアクションメニューの診断を抑制する](media/suppress-diagnostic-from-editor.png)

- **エラー一覧**から

  抑制するルールを選択して右クリックし、[**ソース内/抑制ファイル内** **の @no__t-** 1] を選択します。

  - **ソースで**非表示にすると、 **[変更のプレビュー]** ダイアログが開き、 C#ソースコードに追加された[#pragma 警告](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning)または Visual Basic [#Disable 警告](/dotnet/visual-basic/language-reference/directives/directives)ディレクティブのプレビューが表示されます。

    ![コードファイルでの #pragma 警告の追加のプレビュー](media/pragma-warning-preview.png)

  - **[抑制ファイル内]** を選択すると、 **[変更のプレビュー]** ダイアログが開き、グローバル抑制ファイルに追加された @no__t 2 属性のプレビューが表示されます。

    ![抑制ファイルへの SuppressMessage 属性の追加のプレビュー](media/preview-changes-in-suppression-file.png)

  **[変更のプレビュー]** ダイアログで、 **[適用]** を選択します。

  > [!NOTE]
  > **ソリューションエクスプローラー**に **[抑制]** メニューオプションが表示されない場合、違反はビルドから発生し、ライブ分析は行われない可能性があります。 **エラー一覧**には、ライブコード分析とビルドの両方からの診断または規則違反が表示されます。 ビルド診断は古くなる可能性があるため、たとえば、違反を修正するようにコードを編集してもリビルドされていない場合は、**エラー一覧**からこれらの診断を抑制することはできません。 ライブ分析または IntelliSense からの診断は、常に最新のソースを使用して最新の状態にあり、**エラー一覧**によって抑制できます。 選択した*ビルド*診断を除外するには、**エラー一覧**ソースフィルターを ビルド +  **Intellisense** から **intellisense のみ** に切り替えます。 次に、非表示にする診断を選択し、前述のように続行します。
  >
  > ![Visual Studio でのエラー一覧ソースフィルター](media/error-list-filter.png)

## <a name="command-line-usage"></a>コマンドラインの使用方法

コマンドラインでプロジェクトをビルドすると、次の条件が満たされた場合に、規則違反がビルド出力に表示されます。

- アナライザーは、VSIX 拡張機能としてではなく、Nuget パッケージとしてインストールされます。

- プロジェクトのコードで1つ以上の規則に違反しています。

- 違反しているルールの[重要度](#rule-severity)は、いずれかの**警告**に設定されます。この場合、違反が発生してもビルドは失敗しません。**エラー**の場合は、違反が発生してもビルドは失敗します。

ビルド出力の詳細度は、規則違反が表示されるかどうかには影響しません。 **低**レベルの詳細度でも、ルール違反はビルド出力に表示されます。

> [!TIP]
> *FxCopCmd* 、または**runcodeanalysis**フラグを使用した msbuild を使用してコマンドラインからレガシ分析を実行することに慣れている場合は、コードアナライザーを使用してこれを行う方法を次に示します。

Msbuild を使用してプロジェクトをビルドするときに、コマンドラインでアナライザーの違反を確認するには、次のようなコマンドを実行します。

```cmd
msbuild myproject.csproj /target:rebuild /verbosity:minimal
```

次の図は、アナライザーの規則違反を含むプロジェクトをビルドしたときのコマンドラインビルド出力を示しています。

![ルール違反を示す MSBuild 出力](media/command-line-build-analyzers.png)

## <a name="dependent-projects"></a>依存プロジェクト

.NET Core プロジェクトでは、NuGet アナライザーを含むプロジェクトへの参照を追加すると、それらのアナライザーも依存プロジェクトに自動的に追加されます。 この動作を無効にするには、たとえば、依存プロジェクトが単体テストプロジェクトの場合、 **Privateassets**属性を設定して、参照されるプロジェクトの *.csproj*ファイルまたは *.vbproj*ファイルで NuGet パッケージを private としてマークします。

```xml
<PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers" Version="2.9.0" PrivateAssets="all" />
```

## <a name="see-also"></a>関連項目

- [Visual Studio のコードアナライザーの概要](../code-quality/roslyn-analyzers-overview.md)
- [コードアナライザーのバグを送信する](https://github.com/dotnet/roslyn-analyzers/issues)
- [規則セットを使用する](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [コード分析の警告を表示しない](../code-quality/in-source-suppression-overview.md)
