---
title: Editorconfig を使用して FxCop アナライザーを構成します。
ms.date: 03/11/2019
ms.topic: conceptual
helpviewer_keywords:
- FxCop analyzers, configuring
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ac751b7ec130b6bfbb18752c02b491b6c342f172
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57874700"
---
# <a name="configure-fxcop-analyzers"></a>FxCop アナライザーを構成します。

[FxCop アナライザー](install-fxcop-analyzers.md)静的コード分析、Roslyn アナライザーへの変換から最も重要な"FxCop"規則で構成されます。 2 つの方法では、FxCop コード アナライザーを構成できます。

- [ルール セット](#fxcop-analyzer-rule-sets)、有効またはルールを無効にし、個々 のルール違反の重要度を設定することができます。

- 以降のバージョン 2.6.3、 [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers)を通じて NuGet がパッケージ化、 [.editorconfig ファイル](#editorconfig-file)します。 [構成可能なオプション](fxcop-analyzer-options.md)let のどの部分を絞り込む、コードベースを分析します。

> [!TIP]
> FxCop 静的コード分析と FxCop アナライザーの違いについては、次を参照してください。 [FxCop アナライザー FAQ](fxcop-analyzers-faq.md)します。

## <a name="fxcop-analyzer-rule-sets"></a>FxCop アナライザーの規則セット

FxCop アナライザーを構成する方法の 1 つは、XML を使用して、*ルール セット*します。 規則セットは、対象の問題と特定の条件を識別するコード分析規則のグループです。 規則セットでは、有効またはルールを無効にし、個々 のルール違反の重要度を設定できます。

FxCop アナライザーの NuGet パッケージには、次の規則のカテゴリの定義済みの規則セットが含まれています。

- デザイン
- ドキュメント
- 保守性
- 名前付け
- パフォーマンス
- 信頼性
- セキュリティ
- 使い方

詳細については、次を参照してください。 [Roslyn アナライザーの規則セット](analyzer-rule-sets.md)します。

## <a name="editorconfig-file"></a>EditorConfig ファイル

アナライザーの規則を構成するにはキーと値のペアを追加することで、 [.editorconfig](https://editorconfig.org)ファイル。 構成ファイルを指定できます[、プロジェクトに固有](#per-project-configuration)でもかまいません[共有](#shared-configuration)2 つ以上のプロジェクト間で。

### <a name="per-project-configuration"></a>プロジェクトごとの構成

特定のプロジェクトの .editorconfig ベースのアナライザーの構成を有効にするには追加、 *.editorconfig*ファイルをプロジェクトのルート ディレクトリにします。

> [!TIP]
> .Editorconfig ファイルをプロジェクトに追加するにはでプロジェクトを右クリックして**ソリューション エクスプ ローラー**選択**追加** > **新しい項目の**します。 **新しい項目の追加**ウィンドウで、入力**editorconfig**検索ボックスにします。 選択、 **editorconfig ファイル (既定値)** テンプレートを選択して**追加**します。
>
> ![Visual Studio でプロジェクトに editorconfig 項目を追加します。](media/add-editorconfig-file.png)

現在階層はサポートされていません「結合」.editorconfig ファイルのソリューションとプロジェクト レベルなど、別のディレクトリのレベルに存在します。

### <a name="shared-configuration"></a>共有構成

2 つ以上のプロジェクト間でアナライザーの構成の .editorconfig ファイルを共有することができますが、追加の手順が必要です。

1. 保存、 *.editorconfig*ファイルを一般的な場所にします。

2. 作成、 *.props*ファイルは次の内容。

   ```xml
   <Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <PropertyGroup>
       <SkipDefaultEditorConfigAsAdditionalFile>true</SkipDefaultEditorConfigAsAdditionalFile>
     </PropertyGroup>
     <ItemGroup Condition="Exists('<your path>\.editorconfig')" >
       <AdditionalFiles Include="<your path>\.editorconfig" />
     </ItemGroup>
   </Project>
   ```

3. 行を追加して、 *.csproj*または *.vbproj*をインポートするファイル、 *.props*前の手順で作成したファイル。 この行は、FxCop アナライザーをインポートする行の前に配置する必要があります *.props*ファイル。 たとえば、.props ファイルの名前は*editorconfig.props*:

   ```xml
   ...
   <Import Project="..\..\editorconfig.props" Condition="Exists('..\..\editorconfig.props')" />
   <Import Project="..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.3\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props" Condition="Exists('..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.3\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props')" />
   ...
   ```

4. プロジェクトの再読み込みします。

> [!NOTE]
> .Editorconfig ファイルを使用して、古い FxCop 規則 (静的コード分析は FxCop) を構成することはできません。

## <a name="option-scopes"></a>オプションのスコープ

すべてのルール、(たとえば、名前付けまたはデザイン) ルールのカテゴリまたは特定のルールは、各オプションを構成できます。

### <a name="all-rules"></a>すべてのルール

すべてのルールのオプションを構成するための構文は次のとおりです。

|構文|例|
|-|-|
| dotnet_code_quality します。OptionName OptionValue を = | `dotnet_code_quality.api_surface = public` |

### <a name="category-of-rules"></a>規則のカテゴリ

ためのオプションを構成するための構文を*カテゴリ*(名前付け、デザイン、パフォーマンスなど) ルールのとおりです。

|構文|例|
|-|-|
| dotnet_code_quality します。RuleCategory.OptionName OptionValue を = | `dotnet_code_quality.Naming.api_surface = public` |

### <a name="specific-rule"></a>特定のルール

特定のルールのオプションを構成するための構文は次のとおりです。

|構文|例|
|-|-|
| dotnet_code_quality します。RuleId.OptionName OptionValue を = | `dotnet_code_quality.CA1040.api_surface = public` |

## <a name="see-also"></a>関連項目

- [アナライザーの構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)
- [FxCop アナライザー](install-fxcop-analyzers.md)
