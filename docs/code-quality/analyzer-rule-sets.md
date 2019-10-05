---
title: FxCop アナライザーのルールセット
ms.date: 09/23/2019
ms.topic: conceptual
helpviewer_keywords:
- analyzer packages, rule sets
- rule sets for analyzers
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 313b578743fd734da3354989a8cee16022779242
ms.sourcegitcommit: 39a04f42d23597b70053686d7e927ba78f38a9a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2019
ms.locfileid: "71974703"
---
# <a name="rule-sets-for-analyzer-packages"></a>アナライザー パッケージの規則セット

定義済みの規則セットは、一部の NuGet アナライザーパッケージに含まれています。 たとえば、 [FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/) NuGet analyzer パッケージに含まれている規則セット (バージョン2.6.2 以降) は、セキュリティ、名前付け、パフォーマンスなど、カテゴリに基づいて規則を有効または無効にします。 規則セットを使用すると、特定のカテゴリの規則に関連する規則違反だけを簡単に確認できます。

ルールセットは、対象となる問題と特定の条件を識別するコード分析ルールをグループ化したものです。 ルールセットを使用すると、ルールを有効または無効にしたり、個々のルール違反の重大度を設定したりできます。 FxCop analyzer NuGet パッケージには、次の規則カテゴリの定義済みの規則セットが含まれています。

- デザイン
- ドキュメント
- 保守性
- 名前付け
- パフォーマンス
- 信頼性
- セキュリティ
- 使い方

レガシの "FxCop" 分析から .NET Compiler Platform ベースのコード分析に移行している場合、これらの規則セットを使用すると、[以前に使用したもの](rule-set-reference.md)と同様の規則の構成を引き続き使用できます。

## <a name="use-analyzer-package-rule-sets"></a>アナライザーパッケージの規則セットを使用する

[NuGet analyzer パッケージをインストール](install-roslyn-analyzers.md)したら、*そのルールセットディレクトリで*定義済みのルールセットを見つけます。 たとえば、`Microsoft.CodeAnalysis.FxCopAnalyzers` アナライザーパッケージを参照した場合は、 *% USERPROFILE% \\. nuget\packages\microsoft.codeanalysis.fxcopanalyzers @ no__t @ no__t-6\rulesets*に、その*ルールセット*ディレクトリが見つかります。 そこから、1つまたは複数のルールセットをコピーし、Visual Studio プロジェクトが格納されているディレクトリまたは**ソリューションエクスプローラー**に直接貼り付けます。

また、[定義済みの規則セット](how-to-create-a-custom-rule-set.md)を自分の好みに合わせてカスタマイズすることもできます。 たとえば、1つまたは複数のルールの重要度を変更して、**エラー一覧**に違反がエラーまたは警告として表示されるようにすることができます。

## <a name="set-the-active-rule-set"></a>アクティブな規則セットを設定する

アクティブな規則セットを設定するプロセスは、.NET Core/.NET Standard プロジェクトと .NET Framework プロジェクトのどちらを使用しているかによって若干異なります。

### <a name="net-core"></a>.NET Core

.NET Core または .NET Standard プロジェクトで、分析用のアクティブな規則セットを規則に設定するには、 **CodeAnalysisRuleSet**プロパティをプロジェクトファイルに手動で追加します。 たとえば、次のコードスニペットは、アクティブなルールセットとして `HelloWorld.ruleset` を設定します。

```xml
<PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
  ...
  <CodeAnalysisRuleSet>HelloWorld.ruleset</CodeAnalysisRuleSet>
</PropertyGroup>
```

### <a name="net-framework"></a>.NET Framework

.NET Framework プロジェクトで分析のためのアクティブな規則セットを規則に設定するには、次のようにします。

- **ソリューションエクスプローラー**でプロジェクトを右クリックし、 **[プロパティ]** を選択します。

- プロジェクトのプロパティページで、 **[コード分析]** タブを選択します。

::: moniker range="vs-2017"

- **[この規則セットを実行]** で、 **[参照]** を選択し、プロジェクトディレクトリにコピーした規則セットを選択します。

::: moniker-end

::: moniker range=">=vs-2019"

- **[アクティブな規則]** で **[参照]** を選択し、プロジェクトディレクトリにコピーした規則セットを選択します。

::: moniker-end

   これで、選択した規則セットで有効になっている規則に対する規則違反のみが表示されるようになりました。

## <a name="available-rule-sets"></a>使用可能な規則セット

定義済みアナライザーの規則セットには、パッケージ内のすべての規則に影響を与える3つのルールセットが含まれています。これは、すべてのルールを無効にするものと、各ルールの既定の重大度および有効化設定を許可するルールを no__t します。

- All規則が有効になりました。ルールセット
- All規則が無効になりました。ルールセット
- Allルールの既定値。ルールセット

また、パフォーマンスやセキュリティなど、パッケージ内のルールのカテゴリごとに2つのルールセットがあります。 1つの規則セットによってカテゴリのすべての規則が有効になり、1つの規則セットによって、カテゴリ内の各規則の既定の重大度および有効化の設定が優先されます。

[FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/) NuGet analyzer パッケージには、次のカテゴリのルールセットが含まれています。

- デザイン
- ドキュメント
- 保守性
- 名前付け
- パフォーマンス
- 信頼性
- セキュリティ
- 使い方

## <a name="see-also"></a>関連項目

- [アナライザーに関する FAQ](analyzers-faq.md)
- [.NET Compiler Platform アナライザーの概要](roslyn-analyzers-overview.md)
- [アナライザーのインストール](install-roslyn-analyzers.md)
- [アナライザーの構成](use-roslyn-analyzers.md)
- [規則セットを使用したコード分析規則のグループ化](using-rule-sets-to-group-code-analysis-rules.md)
