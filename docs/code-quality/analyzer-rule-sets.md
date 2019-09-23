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
ms.openlocfilehash: da1567dd088ecc060f031e59827ff33024e9e955
ms.sourcegitcommit: 88f576ac32af31613c1a10c1548275e1ce029f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "71185954"
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

[NuGet analyzer パッケージをインストール](install-roslyn-analyzers.md)したら、*そのルールセットディレクトリで*定義済みのルールセットを見つけます。 `Microsoft.CodeAnalysis.FxCopAnalyzers`たとえば、アナライザーパッケージを参照した場合は、% USERPROFILE% *\\\\. nuget\packages\microsoft.codeanalysis.fxcopanalyzers\<バージョンでそのルールセットディレクトリを見つけることができます。\\>ルールセット*。 そこから、1つまたは複数のルールセットをコピーし、Visual Studio プロジェクトが格納されているディレクトリまたは**ソリューションエクスプローラー**に直接貼り付けます。

また、[定義済みの規則セット](how-to-create-a-custom-rule-set.md)を自分の好みに合わせてカスタマイズすることもできます。 たとえば、1つまたは複数のルールの重要度を変更して、**エラー一覧**に違反がエラーまたは警告として表示されるようにすることができます。

## <a name="set-the-active-rule-set"></a>アクティブな規則セットを設定する

アクティブな規則セットを設定するプロセスは、.NET Core/.NET Standard プロジェクトと .NET Framework プロジェクトのどちらを使用しているかによって若干異なります。

### <a name="net-core"></a>.NET Core

.NET Core または .NET Standard プロジェクトで、分析用のアクティブな規則セットを規則に設定するには、 **CodeAnalysisRuleSet**プロパティをプロジェクトファイルに手動で追加します。 たとえば、次のコードスニペットは、 `HelloWorld.ruleset`アクティブな規則セットとしてを設定します。

```xml
<PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
  ...
  <CodeAnalysisRuleSet>HelloWorld.ruleset</CodeAnalysisRuleSet>
</PropertyGroup>
```

### <a name="net-framework"></a>.NET Framework

.NET Framework のプロジェクトで、分析用のアクティブな規則セットを規則に設定するには**ソリューションエクスプローラー**でプロジェクトを右クリックし、 **[プロパティ]** をクリックします。 プロジェクトのプロパティページで、 **[コード分析]** タブを選択します。 **[この規則セットを実行]** で、 **[参照]** を選択し、プロジェクトディレクトリにコピーした規則セットを選択します。 これで、選択した規則セットで有効になっている規則に対する規則違反のみが表示されるようになりました。

## <a name="available-rule-sets"></a>使用可能な規則セット

定義済みアナライザーの規則セットには、パッケージ&mdash;内のすべての規則に影響する3つの規則セットが含まれています。これにより、すべてを無効にして、各規則の既定の重要度と有効化の設定を受け入れます。

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
