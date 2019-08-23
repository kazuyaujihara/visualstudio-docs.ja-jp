---
title: Roslyn アナライザーを使用したコード分析
ms.date: 03/26/2018
ms.topic: overview
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 2d4a9bfca972f9c57688b19bd872b31ee5997f76
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69550767"
---
# <a name="overview-of-net-compiler-platform-code-analyzers"></a>.NET Compiler Platform コード アナライザーの概要

.NET Compiler Platform ("Roslyn") のアナライザーでは、コードのスタイル、品質と保守容易性、設計、その他の問題が分析されます。 Visual Studio には、ユーザーが入力した C# や Visual Basic のコードを分析する、組み込みのアナライザーのセットが含まれています。 [テキスト エディターの [オプション]](../ide/code-styles-and-code-cleanup.md) ページまたは [.editorconfig ファイル](../ide/editorconfig-code-style-settings-reference.md)で、これらの組み込みアナライザーのユーザー設定を構成します。 Visual Studio 拡張機能または NuGet パッケージとして、追加のアナライザーをインストールできます。

アナライザーでルール違反が見つかった場合は、コード エディター (問題のあるコードの下の "*波線*" として) および **[エラー一覧]** ウィンドウで報告されます。

多くのアナライザー ルール (*診断*) には、1 つ以上の*コード修正*が関連付けられており、これを適用して問題を修正できます。 Visual Studio に組み込まれているアナライザー診断には、それぞれコード修正が関連付けられています。 コード修正は、電球アイコン メニューに、他の種類の[クイック アクション](../ide/quick-actions.md)と共に示されます。 これらのコード修正については、「[共通のクイック アクション](../ide/common-quick-actions.md)」を参照してください。

![アナライザーの違反とクイック アクションのコード修正](../code-quality/media/built-in-analyzer-code-fix.png)

## <a name="net-compiler-platform-based-analysis-versus-legacy-analysis"></a>.NET Compiler Platform ベースの分析と従来の分析の比較

.NET Compiler Platform ("Roslyn") コード分析は、最終的に、マネージド コードに関して[従来分析](../code-quality/code-analysis-for-managed-code-overview.md)に取って代わります。 従来の分析の多くのルールは .NET Compiler Platform ベースのコード アナライザーとして書き換えられています。

従来の分析のルール違反と同様に、.NET Compiler Platform ベースのコード分析の違反は Visual Studio の [エラー一覧] ウィンドウに表示されます。 さらに、.NET Compiler Platform ベースのコード分析の違反は、コード エディターで問題のあるコードの下に "*波線*" としても示されます。 波線の色は、ルールの[重要度設定](../code-quality/use-roslyn-analyzers.md#rule-severity)によって異なります。 次のスクリーンショットには、3 つの違反 (赤色、緑色、灰色が 1 つずつ) が示されています。

![コード エディターの波線](media/diagnostics-severity-colors.png)

.NET Compiler Platform ベースの分析アナライザーでは、有効になっている場合、従来の分析と同様に、ビルド時にコードが分析されますが、入力中もライブ状態になります。 [完全ソリューション解析](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md#to-toggle-full-solution-analysis)を有効にした場合、コード アナライザーではエディターで開かれていないコード ファイルを設計時に解析することもできます。

> [!TIP]
> コード アナライザーからのビルド時のエラーと警告が表示されるのは、アナライザーが NuGet パッケージとしてインストールされている場合のみです。

.NET Compiler Platform ベースのコード アナライザーでは、従来の分析で報告されるものと同じ種類の問題が報告されるだけでなく、ファイルやプロジェクトで発生した違反の 1 つ、またはすべてを簡単に修正できます。 これらのアクションを*コード修正*と呼びます。 コード修正は IDE に固有のものです。Visual Studio では、[クイック アクション](../ide/quick-actions.md)として実装されます。 すべてのアナライザー診断にコード修正が関連付けられているわけではありません。

> [!NOTE]
> 次の UI オプションは、従来の分析のみに適用されます。
>
> - **[分析]**  >  **[コード分析の実行]** メニュー オプション。
> - プロジェクトのプロパティ ページの **[コード分析]** タブにある **[ビルドに対するコード分析の有効化]** チェックボックスと **[生成されたコードの結果を表示しない]** チェックボックス。

[エラー一覧] ウィンドウでコード アナライザーの違反と従来の分析の違反を区別するには、 **[ツール]** 列を確認します。 **ソリューション エクスプローラー**のアナライザー アセンブリのいずれかが [ツール] の値 (**Microsoft.CodeQuality.Analyzers** など) と一致する場合、違反はコード アナライザーからのものです。 それ以外の場合、違反は従来の分析からのものです。

![[エラー一覧] の [ツール] 列](media/code-analysis-tool-in-error-list.png)

> [!TIP]
> プロジェクト ファイルにある **RunCodeAnalysis** msbuild プロパティは、従来の分析のみに適用されます。 アナライザーをインストールする場合、プロジェクト ファイルにある **RunCodeAnalysis** を **false** に設定し、従来の分析がビルド後に実行されないようにします。
>
> ```xml
> <RunCodeAnalysis>false</RunCodeAnalysis>
> ```

## <a name="nuget-package-versus-vsix-extension"></a>NuGet パッケージと VSIX 拡張機能

.NET Compiler Platform アナライザーは、NuGet パッケージを介してプロジェクトごとに、または Visual Studio 拡張機能として Visual Studio 全体にインストールすることができます。 [アナライザーをインストールする](../code-quality/install-roslyn-analyzers.md)これら 2 つの方法には、主な動作の違いがいくつかあります。

### <a name="scope"></a>スコープ

Visual Studio 拡張機能としてアナライザーをインストールする場合、ソリューション レベルで Visual Studio のすべてのインスタンスに適用されます。 NuGet パッケージとしてアナライザーをインストールする (推奨される方法) 場合、NuGet パッケージがインストールされたプロジェクトにのみ適用されます。 チーム環境では、NuGet パッケージとしてインストールされたアナライザーは、そのプロジェクトで作業する*すべての開発者* のスコープ内にあります。

### <a name="build-errors"></a>ビルド エラー

継続的インテグレーション (CI) ビルドの一部として、あるいはコマンド ラインを使用するなどして、ビルド時にルールを適用するには、NuGet パッケージとしてアナライザーをインストールします。 拡張機能としてアナライザーをインストールする場合、アナライザーの警告とエラーはビルド レポートに示されません。

次のスクリーンショットは、アナライザー ルール違反を含むプロジェクトのビルドからのコマンドライン ビルド出力を示しています。

![ルール違反を示す MSBuild 出力](media/command-line-build-analyzers.png)

### <a name="rule-severity"></a>ルールの重要度

Visual Studio 拡張機能としてインストールされたアナライザーからルールの重要度を設定することはできません。 [ルールの重要度](../code-quality/use-roslyn-analyzers.md#rule-severity)を構成するには、NuGet パッケージとしてアナライザーをインストールします。

## <a name="categories"></a>カテゴリ

コードの分析に役立つさまざまな種類のアナライザーを次に示します。

- Microsoft が推奨するアナライザー: [FXCop アナライザー](../code-quality/fxcop-analyzers.yml)
- Visual Studio IDE アナライザー: [EditorConfig](../ide/code-styles-and-code-cleanup.md)
- サード パーティのアナライザー: [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/)、[Roslynator](https://www.nuget.org/packages/Roslynator/)、[XUnit アナライザー](https://www.nuget.org/packages/xunit.analyzers/)、[Sonar アナライザー](https://www.nuget.org/packages/SonarAnalyzer.CSharp/)

## <a name="next-steps"></a>次の手順

> [!div class="nextstepaction"]
> [Visual Studio にコード アナライザーをインストールする](../code-quality/install-roslyn-analyzers.md)

> [!div class="nextstepaction"]
> [Visual Studio でコード アナライザーを使用する](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>関連項目

- [アナライザーに関する FAQ](analyzers-faq.md)
- [独自のコード アナライザーを作成する](../extensibility/getting-started-with-roslyn-analyzers.md)
- [.NET Compiler Platform SDK](/dotnet/csharp/roslyn-sdk/)
