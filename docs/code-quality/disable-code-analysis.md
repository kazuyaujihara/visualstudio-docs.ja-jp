---
title: コード分析を無効にする
ms.date: 10/03/2019
ms.topic: conceptual
helpviewer_keywords:
- code analysis, disable
- disable code analysis
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 77c189e4a15f2ae4049c45d2c8463079895f5be2
ms.sourcegitcommit: 39a04f42d23597b70053686d7e927ba78f38a9a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2019
ms.locfileid: "71975146"
---
# <a name="how-to-disable-source-code-analysis-for-managed-code"></a>マネージコードのソースコード分析を無効にする方法

::: moniker range=">=vs-2019"

このページを使用すると、Visual Studio でコード分析を無効にすることができます。 無効にできるものには制限があります。また、コード分析を無効にする手順は、いくつかの要因によって異なります。

- プロジェクトの種類 (.NET Core/Standard と .NET Framework)

  .NET Core および .NET Standard プロジェクトには、NuGet パッケージとしてインストールされたアナライザーからのコード分析を無効にするための [コード分析のプロパティ] ページにオプションがあります。 詳細については、「 [.Net Core と .NET Standard のプロジェクト](#net-core-and-net-standard-projects)」を参照してください。 .NET Framework プロジェクトのソースコード分析を無効にするには、「[プロジェクトの .NET Framework](#net-framework-projects)」を参照してください。

- NuGet アナライザーパッケージと VSIX または組み込みアナライザー

  現時点では、組み込みアナライザーのライブコード分析 (ルール ID IDE0067 など) を無効にすることはできません。 同様に、Visual Studio 拡張機能 (VSIX) の一部としてインストールされたアナライザーのライブコード分析を無効にすることはできません。 組み込みおよび VSIX ベースのアナライザーからのエラーおよび警告を非表示にするには、メニューバーの [@no__t の**分析**] を選択し、**アクティブな問題**を非表示にします。 NuGet パッケージの一部としてインストールされているアナライザーのライブおよびビルド時の分析を無効にする*ことができ*ます。

- ソース分析と従来の分析

  このトピックは、レガシ (バイナリ) 分析ではなく、ソースコード分析に適用されます。 レガシ分析を無効にする方法の詳細については、@no__t を参照してください。レガシコード分析 @ no__t を有効または無効にします。

## <a name="net-core-and-net-standard-projects"></a>.NET Core と .NET Standard のプロジェクト

Visual Studio 2019 バージョン16.3 以降では、[コード分析] プロパティページで使用できるチェックボックスが2つあります。これを使用すると、NuGet ベースのアナライザーをビルド時に実行するか、デザイン時に実行するかを制御できます。 これらのオプションはプロジェクトに固有です。

![Visual Studio でライブコード分析またはビルドを有効または無効にする](media/run-on-build-run-live-analysis.png)

このページを開くには、**ソリューションエクスプローラー**でプロジェクトノードを右クリックし、 **[プロパティ]** を選択します。 **[コード分析]** タブを選択します。

- ビルド時にソース分析を無効にするには、 **[ビルド時に実行**] オプションをオフにします。
- ライブソース分析を無効にするには、 **[ライブ分析で実行**する] オプションをオフにします。

> [!NOTE]
> **[ライブ分析で実行]** がオフになっている場合でも、組み込みのアナライザーと VSIX ベースのアナライザーによってコードのライブ分析が継続されます。 これらのアナライザーからのエラーおよび警告を非表示にするには、メニューバーの [@no__t の**分析**] を選択し、**アクティブな問題**を非表示にします。

## <a name="net-framework-projects"></a>.NET Framework プロジェクト

NuGet パッケージの一部としてインストールされているアナライザーのソースコード分析をオフにするには、次の MSBuild プロパティの1つまたは複数を[プロジェクトファイル](../ide/solutions-and-projects-in-visual-studio.md#project-file)に追加します。

| MSBuild プロパティ | 説明 | 既定 |
| - | - | - |
| `RunAnalyzersDuringBuild` | NuGet ベースのアナライザーをビルド時に実行するかどうかを制御します。 | `true` |
| `RunAnalyzersDuringLiveAnalysis` | デザイン時に NuGet ベースのアナライザーがコードをライブで分析するかどうかを制御します。 | `true` |
| `RunAnalyzers` | ビルド時とデザイン時の両方で NuGet ベースのアナライザーを無効にします。 このプロパティは `RunAnalyzersDuringBuild` と `RunAnalyzersDuringLiveAnalysis` よりも優先されます。 | `true` |

例 :

```xml
<RunAnalyzersDuringBuild>false</RunAnalyzersDuringBuild>
<RunAnalyzersDuringLiveAnalysis>false</RunAnalyzersDuringLiveAnalysis>
<RunAnalyzers>false</RunAnalyzers>
```

::: moniker-end

::: moniker range="vs-2017"

## <a name="source-analysis"></a>ソース解析

Visual Studio 2017 では、[ソース分析](roslyn-analyzers-overview.md)を無効にすることはできません。 エラー一覧からアナライザーのエラーをクリアする場合は、[@no__t**分析**] を選択して現在のすべての違反を抑制するか、メニューバーで [**コード分析を実行し、アクティブな問題を非**表示にする] を選択します。 詳細については、「[違反の抑制](use-roslyn-analyzers.md#suppress-violations)」を参照してください。

Visual Studio 2019 バージョン16.3 以降では、NuGet ベースのソースコード分析を無効にすることができます。 Visual Studio 2019 へのアップグレードを検討してください。

## <a name="legacy-analysis"></a>レガシ分析

[**コード分析**のプロパティ] ページで、レガシのビルド時分析を無効にすることができます。 詳細については、「[方法 :レガシコード分析 @ no__t を有効または無効にします。

::: moniker-end

## <a name="see-also"></a>関連項目

- [違反を抑制する](use-roslyn-analyzers.md#suppress-violations)
- [2 つのオブジェクトが等しいかどうかをテストする方法レガシコード分析を有効または無効にする @ no__t-0
