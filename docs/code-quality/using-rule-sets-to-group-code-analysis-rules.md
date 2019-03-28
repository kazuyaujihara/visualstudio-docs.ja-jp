---
title: コード分析規則セット
ms.date: 04/02/2018
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.learnmore
helpviewer_keywords:
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c95b442835289265d197b6806c6d87fa051f2c1b
ms.sourcegitcommit: d78821f8c353e0102b1554719f549f32dffac71b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "58515234"
---
# <a name="use-rule-sets-to-group-code-analysis-rules"></a>コード分析規則のグループに規則を使用を設定します。

Visual Studio でコード分析を構成するときに、組み込みの*規則セット*一覧から選択することができます。 規則セットは、対象の問題とそのプロジェクトの特定の条件を識別するコード分析規則のグループです。 たとえば、パブリックに利用可能な Api のコードをスキャンするように設計が規則セットを適用できます。 利用可能なすべてのルールを含む規則セットを適用することもできます。

ルール セットを追加または削除ルールまたはルールの重大度を変更することで警告またはエラーのいずれかとして表示をカスタマイズすることができます、**エラー一覧**します。 カスタマイズした規則セットで、特定の開発環境の要件を満たすことができます。 規則セットをカスタマイズするときに、規則セット エディターは、検索とフィルター処理、プロセスに役立つツールを提供します。

規則セットには[マネージ コードのスタティック分析](how-to-configure-code-analysis-for-a-managed-code-project.md)、 [C++ コードの分析](using-rule-sets-to-specify-the-cpp-rules-to-run.md)、および[Roslyn アナライザー](analyzer-rule-sets.md)があります。

## <a name="rule-set-format"></a>規則セットの形式

規則セットは、 XML 形式で指定した、 *.ruleset*ファイルです。 規則には、ID が振られ、*アクション*、アナライザー ID と、ファイルの名前空間ごとに分類されます。

*.ruleset*ファイルの内容は、この xml のようになります。

```xml
<RuleSet Name="Rules for Hello World project" Description="These rules focus on critical issues for the Hello World app." ToolsVersion="10.0">
  <Localization ResourceAssembly="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.dll" ResourceBaseName="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.Localized">
    <Name Resource="HelloWorldRules_Name" />
    <Description Resource="HelloWorldRules_Description" />
  </Localization>
  <Rules AnalyzerId="Microsoft.Analyzers.ManagedCodeAnalysis" RuleNamespace="Microsoft.Rules.Managed">
    <Rule Id="CA1001" Action="Warning" />
    <Rule Id="CA1009" Action="Warning" />
    <Rule Id="CA1016" Action="Warning" />
    <Rule Id="CA1033" Action="Warning" />
  </Rules>
  <Rules AnalyzerId="Microsoft.CodeQuality.Analyzers" RuleNamespace="Microsoft.CodeQuality.Analyzers">
    <Rule Id="CA1802" Action="Error" />
    <Rule Id="CA1814" Action="Info" />
    <Rule Id="CA1823" Action="None" />
    <Rule Id="CA2217" Action="Warning" />
  </Rules>
</RuleSet>
```

> [!TIP]
> グラフィカルな**規則セット エディター**の[規則セットの編集](../code-quality/working-in-the-code-analysis-rule-set-editor.md)を使用すると、手動より簡単に編集できます。

## <a name="specify-a-rule-set-for-a-project"></a>プロジェクトに対して規則セットの指定します。

プロジェクトの規則セットは Visual Studio プロジェクトファイルの **CodeAnalysisRuleSet** プロパティで指定されます。 例えば:

```xml
<PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
  ...
  <CodeAnalysisRuleSet>HelloWorld.ruleset</CodeAnalysisRuleSet>
</PropertyGroup>
```

## <a name="see-also"></a>関連項目

- [コード分析規則セットの参照](../code-quality/rule-set-reference.md)