---
title: .NET 開発の生産性を向上させる
description: より良い .NET コードをより早く書き込むのに役立つ、移動、コード分析、単体テスト、およびその他の機能の概要。
author: kuhlenh
ms.author: gewarren
manager: jillfra
ms.date: 03/26/2019
ms.topic: conceptual
helpviewer_keywords:
- editor
ms.workload:
- dotnet
ms.openlocfilehash: 07584f9e04be805ed699676c678b2147ec3679ff
ms.sourcegitcommit: cd91a8a4f6086cda9ba6948be25864fc7d6b8e44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2019
ms.locfileid: "59537625"
---
# <a name="visual-studio-productivity-guide-for-c-developers"></a>C# 開発者のための Visual Studio 生産性ガイド

Visual Studio によって開発者の生産性がどのように向上するかを説明します。 逆コンパイルされたアセンブリへの移動、入力時の変数名の提案、**テスト エクスプローラー**の階層ビュー、ファイル/型/メンバー/シンボルの宣言に移動するための [すべてに移動] (**Ctrl** + **T**)、インテリジェントな**例外ヘルパー**、コード スタイルの構成と適用、多くのリファクタリングとコード修正など、パフォーマンスと生産性を向上させる機能を利用できます。

## <a name="im-used-to-keyboard-shortcuts-from-a-different-editor"></a>別の拡張機能のキーボード ショートカットを使い慣れています

::: moniker range="vs-2017"

**Visual Studio 2017 バージョン 15.8 の新機能**

::: moniker-end

別の IDE やコーディング環境から切り替えた場合は、キーボード スキームを *Visual Studio Code* または *ReSharper (Visual Studio)* に変更できます。

![Visual Studio のキーボード スキーム](../ide/media/VS2017Guide-Keyboard.png)

次の一部の拡張機能でも、キーボード スキームが提供されます。

- [Visual Studio のホット キー (ReSharper/IntelliJ)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [Emacs エミュレーション](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

よく使用される Visual Studio のショートカットを以下に示します。

| ショートカット (すべてのプロファイル) | コマンド | 説明 |
|-|-|-|
| **Ctrl** + **T** | すべてにジャンプ | 任意のファイル、型、メンバー、またはシンボルの宣言に移動します |
| **F12** (**Ctrl**+**クリック**でも可能) | [定義へ移動] | シンボルが定義されている場所に移動します |
| **Ctrl** + **F12** | 実装に移動 | 基本データ型またはメンバーから、さまざまな実装に移動します |
| **Shift** + **F12** | [すべての参照の検索] | すべてのシンボルまたはリテラルの参照を表示します |
| **Ctrl**+**.** (C# Profile では **Alt** + **Enter** でも可能) | クイック アクションとリファクタリング | そのカーソル位置またはコード選択で、どのコード修正、コード生成アクション、リファクタリング、その他クイック アクションが使用できるかを表示します |
| **Ctrl** + **D** | 行の複製 | カーソルのあるコード行を複製します (**Visual Studio 2017 バージョン 15.6** 以降で使用可能) |
| **Shift** + **Alt** + **+**/**-** | 選択範囲の拡大/縮小 | エディターの現在の選択範囲を拡大または縮小します (**Visual Studio 2017 バージョン 15.5** 以降で使用できます) |
| **Shift**  +  **Alt**  +  **.** | 次の一致にキャレットを挿入 | 現在の選択範囲と一致する次の場所で選択内容とキャレットを追加します (**Visual Studio 2017 バージョン 15.8** 以降で利用可能)。 |
| **Ctrl** + **Q** | 検索 | すべての Visual Studio の設定を検索します |
| **F5** | デバッグの開始 | アプリケーションのデバッグを開始します |
| **Ctrl** + **F5** | デバッグなしで開始 | デバッグなしでアプリケーションをローカルで実行します |
| **Ctrl** + **K**、**D** (既定のプロファイル) または **Ctrl** + **E**、**D** (C# Profile) | [ドキュメントのフォーマット](code-styles-and-quick-actions.md#format-document-command) | 改行文字、間隔、およびインデント設定に基づき、ファイルの書式設定の違反をクリーンアップします |
| **Ctrl** + **\\**、**Ctrl** + **E** (既定のプロファイル) または **Ctrl** + **W**、**E** (C# Profile) | エラー一覧の表示 | ドキュメント、プロジェクト、またはソリューション内のすべてのエラーを表示します |
| **Alt**  +  **PgUp/PgDn** | 次/前の問題に移動 | ドキュメント内の前/次のエラー、警告、提案に移動します (**Visual Studio 2017 バージョン 15.8** 以降で利用可能)。 |

> [!NOTE]
> 一部の拡張機能によって、既定の Visual Studio キー バインドがバインド解除されます。 上記のコマンドを使用するには、**[ツール]** > **[設定のインポートとエクスポート]** > **[すべての設定をリセット]** または **[ツール]** > **[オプション]** > **[キーボード]** > **[リセット]** の順に進み、キー バインドを Visual Studio の既定値に復元します。

キーボード ショートカットとコマンドの詳細については、「[キーボード ショートカット](../ide/tips-and-tricks-for-visual-studio.md)」を参照してください。

## <a name="navigate-quickly-to-files-or-types"></a>ファイルまたは型にすばやく移動する

Visual Studio 2017 には、"**すべてに移動**" という機能があります (**Ctrl** + **T**)。 **[すべてに移動]** を使うと、ファイル、型、メンバー、またはシンボルの宣言にすばやく移動できます。

- **歯車**アイコンを使用して、この検索バーの場所を変更したり、ライブ ナビゲーション プレビューをオフにしたりします。
- `t mytype` などの構文を使用して、結果をフィルター処理します。
- 検索の範囲を現在のドキュメントだけにします。
- キャメル ケースの一致がサポートされています。

![Visual Studio の [すべてに移動]](../ide/media/VS2017Guide-go-to-all.png)

## <a name="enforce-code-style-rules-on-a-codebase"></a>コードベースにコード スタイル規則を適用する

*.editorconfig* ファイルを使って、コーディング規則を体系化し、ソースとともに移動させることができます。

::: moniker range="vs-2017"

- Visual Studio の *.editorconfig* ファイルの追加と編集が簡単になる、[EditorConfig 言語サービス拡張機能](https://aka.ms/editorconfig)をインストールできます。

::: moniker-end

::: moniker range=">=vs-2019"

- **[ツール]** > **[オプション]** > **[テキスト エディター]** > **[C#]** > **[コード スタイル]** のコード スタイルの設定から、*.editorconfig* ファイルを自動的に作成します。

   ![VS 2019 で設定から editorconfig ファイルを生成する](media/vs-2019/generate-editorconfig-file.png)

::: moniker-end

- [Visual Studio の IntelliCode 拡張機能](/visualstudio/intellicode/intellicode-visual-studio)をお試しください。 この実験的な拡張機能では、ユーザーのコード スタイルが既存のコードから推測され、既に定義したコード スタイルの設定を使用して空でない *.editorconfig* ファイルが作成されます。

- .NET コーディング規則オプションに関する[ドキュメント](editorconfig-code-style-settings-reference.md)を確認してください。

- *.editorconfig* ファイルの例については[こちら](https://gist.github.com/kuhlenh/5471666a7a2c57fea427e81cf0a41da8)をご覧ください。

![Visual Studio でのコード スタイルの適用](../ide/media/VSGuide_CodeStyle.png)

## <a name="refactorings-and-code-fixes"></a>リファクタリングとコード修正

Visual Studio には、多くのリファクタリング、コード生成アクション、およびコード修正が含まれています。 赤の波線はエラー、緑の波線は警告、3 つのグレーの点はコード提案をそれぞれ表します。 コード修正にアクセスするには、電球またはねじ回しのアイコンをクリックするか、**Ctrl** + **.** キー または **Alt** + **Enter** キーを押します。 各修正にはプレビュー ウィンドウが付属しており、修正の効果によるライブ コードの相違が示されます。

一般的なクイック修正とリファクタリングには、次の内容が含まれます。

- *名前の変更*
- *メソッドの抽出*
- *メソッド シグネチャの変更*
- *コンストラクターの生成*
- *メソッドの生成*
- *ファイルへの型の移動*
- *Null チェックの追加*
- *パラメーターの追加*
- *不要な using の削除*
- *LINQ クエリまたは LINQ メソッドへの foreach ループ*
- *メンバーのプル アップ*
- 詳細については、「[コード生成機能](code-generation-in-visual-studio.md)」を参照してください。

[FxCop アナライザーをインストール](../code-quality/install-fxcop-analyzers.md)して、コードの問題にフラグを設定できます。 または、[Roslyn アナライザー](https://github.com/dotnet/roslyn/wiki/Getting-Started-Writing-a-Custom-Analyzer-&-Code-Fix)を使用して、独自のリファクタリングまたはコード修正を記述します。

さまざまなコミュニティのメンバーが、さらにコードの検査を追加する無料の拡張機能を作成しています。

- [Roslynator](https://marketplace.visualstudio.com/items?itemName=josefpihrt.Roslynator2017)
- [SonarLint for Visual Studio](https://marketplace.visualstudio.com/items?itemName=SonarSource.SonarLintforVisualStudio2017)
- [StyleCopAnalyzers](https://www.nuget.org/packages/stylecop.analyzers/)
- [CodeCracker](https://www.nuget.org/packages/codecracker.CSharp/)

![Visual Studio でのリファクタリング](../ide/media/VSGuide_CodeAnalysis.png)

## <a name="find-usages-go-to-implementation-and-navigate-to-decompiled-assemblies"></a>使用状況の検索、実装への移動、および逆コンパイルされたアセンブリへの移動

Visual Studio には、コードの検索と[移動](../ide/navigating-code.md)に役立つ多くの機能があります。

| 機能 | ショートカット | 詳細/機能強化 |
|- | - | -|
| [すべての参照の検索] | **Shift** + **F12**| 結果は、プロジェクト、定義、および参照型によって、色分け表示してグループ化できます (読み取りや書き込みなど)。 結果を "ロックする" こともできます。 |
| 実装に移動 | **Ctrl** + **F12** | オーバーライドされたメンバーに移動するには、`override` キーワードの [定義へ移動] を使用します |
| [定義へ移動] | **F12** または **Ctrl**+**クリック**| **Ctrl** キーを押しながらクリックすると、定義に移動します |
| 定義をここに表示 | **Alt** + **F12** | 定義のインライン ビュー |
| 構造ビジュアライザー | 中かっこの間の灰色の点線 | マウス ポインターを合わせると、コードの構造を参照できます |
| 逆コンパイルされたアセンブリへの移動 | **F12** または **Ctrl**+**クリック** | (ILSpy によって逆コンパイルされた) 外部リソースに移動します。その場合、**[ツール]** > **[オプション]** > **[テキスト エディター]** > **[C#]** > **[詳細設定]** > **[逆コンパイルされたソースへのナビゲーションを有効にする]** で機能を有効にします。 |

![[すべてに移動] および [すべての参照の検索]](../ide/media/VSIDE_Productivity_Navigation.png)

## <a name="improved-intellisense"></a>強化された IntelliSense

単なるアルファベット順の一覧ではなく、[文脈に合わせたコードの入力候補](/visualstudio/intellicode/intellicode-visual-studio)を取得するには、[IntelliCode 拡張機能](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.VSIntelliCode)をダウンロードします。 ご自身のドメイン固有のライブラリに基づいて、[カスタム IntelliSense モデル](/visualstudio/intellicode/custom-model-faq)をトレーニングすることもできます。

## <a name="unit-testing"></a>単体テスト

Visual Studio 2017 以降、テストの操作性に多数の機能強化が行われています。 MSTest v1、MSTest v2、NUnit、または XUnit テスト フレームワークでテストできます。

- **テスト エクスプローラー**でのテスト検出は高速で実行されます。
- **テスト エクスプローラー**で*階層的な並べ替え*を使用して、テストを整理します。
- [Live Unit Testing](../test/live-unit-testing.md) は、コードの変更によって影響を受けたテストを継続的に実行して、テストの状態を通知するインライン エディターのアイコンを更新します。 ライブ テスト セットに特定のテストまたはテスト プロジェクトを含めるか除外します。

![Visual Studio のテスト エクスプローラーの階層ビュー](../ide/media/VSGuide_Testing.png)

## <a name="debugging"></a>デバッグ

Visual Studio のデバッグ機能のいくつかを次に示します。

::: moniker range=">=vs-2019"

- **Watch**、**Autos**、および **Locals** の各ウィンドウでの文字列検索機能。
- *クリックで実行*。コード行の横にマウス ポインターを移動すると緑色の [再生] アイコンが表示され、それをクリックすると、その行に達するまでプログラムを実行できます。
- **例外ヘルパー**。最も重要な情報をダイアログの最上位に配置します (たとえば、`NullReferenceException` でどの変数が `null` なのか)。
- [デバッグのステップ バック](../debugger/view-historical-application-state.md)。前のブレークポイントまたはステップに戻り、過去のアプリケーションの状態を確認できます。
- [スナップショットのデバッグ](/azure/application-insights/app-insights-snapshot-debugger)。例外がスローされた時点のライブ Web アプリケーションの状態を調べることができます (Azure 上でスローされる必要があります)。

::: moniker-end

::: moniker range="vs-2017"

- *クリックで実行*。コード行の横にマウス ポインターを移動すると緑色の [再生] アイコンが表示され、それをクリックすると、その行に達するまでプログラムを実行できます。
- **例外ヘルパー**。最も重要な情報をダイアログの最上位に配置します (たとえば、`NullReferenceException` でどの変数が `null` なのか)。
- [デバッグのステップ バック](../debugger/view-historical-application-state.md)。前のブレークポイントまたはステップに戻り、過去のアプリケーションの状態を確認できます。
- [スナップショットのデバッグ](/azure/application-insights/app-insights-snapshot-debugger)。例外がスローされた時点のライブ Web アプリケーションの状態を調べることができます (Azure 上でスローされる必要があります)。

::: moniker-end

![Visual Studio の例外ヘルパー](../ide/media/VSGuide_Debugging.png)

## <a name="version-control"></a>バージョン管理

Git または TFVC を使用して Visual Studio でコードを格納して更新することができます。

::: moniker range=">=vs-2019"

- [Pull requests for Visual Studio](https://marketplace.visualstudio.com/items?itemName=vsideversioncontrolmsft.pr4vs) をインストールして、Visual Studio を離れずに pull request を作成、レビュー、およびチェック アウトします。

::: moniker-end

- [チーム エクスプローラー](reference/team-explorer-reference.md)でローカルの変更を整理し、ステータス バーを使用して保留中のコミットと変更を追跡します。

- [Continuous Delivery Tools for Visual Studio](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) 拡張機能を使用して、Visual Studio 内で ASP.NET プロジェクトの継続的インテグレーションと継続的デリバリーを設定します。

![Visual Studio におけるソース管理](../ide/media/VSIDE_Productivity_SourceControl.png)

## <a name="what-other-features-should-i-know-about"></a>他にどのような機能について知っておく必要がありますか?

コードをいっそう効率的に記述できるようになるエディターと生産性の機能の一覧を次に示します。 一部の機能は既定ではオフになっているので、有効にする必要があります (これらは、お使いのコンピューター上でインデックスを作成する機能、検討中の機能、または現在実験段階の機能である可能性があります)。

| 機能 | 説明 | 有効にする方法 |
|-|-|-|
| ソリューション エクスプローラーでファイルを探す | **ソリューション エクスプローラー**で作業中のファイルを強調表示する | **[ツール]** > **[オプション]** > **[プロジェクトとソリューション]** > **[アクティブな項目をソリューション エクスプローラーで選択された状態にする]** |
| 参照アセンブリと NuGet パッケージの型に using を追加する | 参照されていない型の NuGet パッケージをインストールするためのコード修正を含むエラー電球を表示します | **[ツール]** > **[オプション]** > **[テキスト エディター]** > **[C#]** > **[詳細設定]** > **[参照アセンブリの型に using を提案する]** および **[NuGet パッケージの型に using を提案する]** |
| 完全ソリューション解析を有効にする | **エラー一覧**にソリューション内のすべてのエラーを表示します | **[ツール]** > **[オプション]** > **[テキスト エディター]** > **[C#]** > **[詳細設定]** > **[完全ソリューション解析を有効にする]** |
| 逆コンパイルされたソースへの移動を有効にする | 外部ソースからの型/メンバーの [定義に移動] が可能になり、ILSpy 逆コンパイラを使ってメソッド本体を表示できます | **[ツール]** > **[オプション]** > **[テキスト エディター]** > **[C#]** > **[詳細設定]** > **[逆コンパイルされたソースへのナビゲーションを有効にする]** |
| 補完/提案モード | IntelliSense のテキスト補完の動作を変更します。 IntelliJ の知識がある開発者が、既定ではない動作を使用するのに役立ちます。 | **[メニュー]** > **[編集]** > **[IntelliSense]** > **[完了モードの切り替え]** |
| [CodeLens](../ide/find-code-changes-and-other-history-with-codelens.md) | コードの参照情報と変更履歴をエディターに表示します | **[ツール]** > **[オプション]** > **[テキスト エディター]** > **[すべての言語]** > **[CodeLens]** |
| [コード スニペット](../ide/visual-csharp-code-snippets.md) | 一般的な定型コードをスタブできるようにします | スニペットの名前を入力し、**Tab** キーを 2 回押します。 |
