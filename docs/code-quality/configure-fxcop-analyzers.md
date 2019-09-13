---
title: Editorconfig を使用した FxCop アナライザーの構成
ms.date: 03/11/2019
ms.topic: conceptual
helpviewer_keywords:
- FxCop analyzers, configuring
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 68c175a55c9e60e870a5466a831aaae50d62dced
ms.sourcegitcommit: 9c07ae6fb18204ea080c8248994a683fa12e5c82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70293450"
---
# <a name="configure-fxcop-analyzers"></a>FxCop アナライザーの構成

[Fxcop アナライザー](install-fxcop-analyzers.md)は、レガシ分析からの最も重要な "fxcop" ルールで構成され、.NET Compiler Platform ベースのコードアナライザーに変換されます。 FxCop コードアナライザーは、次の2つの方法で構成できます。

- ルール[セット](#fxcop-analyzer-rule-sets)を使用して、ルールを有効または無効にしたり、個々のルール違反の重大度を設定したりできます。

- [FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) NuGet パッケージのバージョン2.6.3 から、 [editorconfig ファイル](#editorconfig-file)を介して開始します。 [構成可能なオプション](fxcop-analyzer-options.md)を使用すると、コードベースのどの部分を分析するかを調整できます。

> [!TIP]
> レガシ分析と FxCop アナライザーの違いについては、「 [fxcop アナライザー](fxcop-analyzers-faq.md)に関する FAQ」を参照してください。

## <a name="fxcop-analyzer-rule-sets"></a>FxCop アナライザーのルールセット

FxCop アナライザーを構成する方法の1つは、XML*規則セット*を使用することです。 ルールセットは、対象となる問題と特定の条件を識別するコード分析ルールをグループ化したものです。 ルールセットを使用すると、ルールを有効または無効にしたり、個々のルール違反の重大度を設定したりできます。

FxCop analyzer NuGet パッケージには、次の規則カテゴリの定義済みの規則セットが含まれています。

- デザイン
- ドキュメント
- 保守性
- 名前付け
- パフォーマンス
- 信頼性
- セキュリティ
- 使い方

詳細については、「[コードアナライザーの規則セット](analyzer-rule-sets.md)」を参照してください。

## <a name="editorconfig-file"></a>EditorConfig ファイル

FxCop アナライザーの規則を構成するには、キーと値のペアを[editorconfig](https://editorconfig.org)ファイルに追加します。 構成ファイルは、[プロジェクトに固有](#per-project-configuration)のものもあれば、2つ以上のプロジェクト間で[共有](#shared-configuration)することもできます。

> [!NOTE]
> Editorconfig ファイルを使用して、従来の FxCop 規則を構成することはできません。

### <a name="per-project-configuration"></a>プロジェクトごとの構成

特定のプロジェクトに対して editorconfig ベースのアナライザーの構成を有効にするには、プロジェクトのルートディレクトリに*editorconfig*ファイルを追加します。

> [!TIP]
> Editorconfig ファイルをプロジェクトに追加するには、**ソリューションエクスプローラー**でプロジェクトを右クリックし、[**新しい項目**の**追加** > ] を選択します。 **[新しい項目の追加]** ウィンドウで、検索ボックスに「 **editorconfig** 」と入力します。 **[Editorconfig ファイル (既定)]** テンプレートを選択し、 **[追加]** を選択します。
>
> ![Visual Studio で editorconfig 項目をプロジェクトに追加する](media/add-editorconfig-file.png)

現在、ソリューションレベルやプロジェクトレベルなど、異なるディレクトリレベルに存在する editorconfig ファイルを "結合" するための階層的なサポートはありません。

### <a name="shared-configuration"></a>共有構成

FxCop アナライザーの構成ファイルは2つ以上のプロジェクト間で共有できますが、いくつかの追加の手順が必要です。

1. *Editorconfig*ファイルを共通の場所に保存します。

2. 次の内容を含む props ファイルを作成*し*ます。

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

3. *.Csproj*ファイルまたは *.vbproj*ファイルに行を追加して、前の手順で作成した*props*ファイルをインポートします。 この行は、FxCop アナライザーの*props*ファイルをインポートする行の前に配置する必要があります。 たとえば、props ファイルに*editorconfig. props*という名前が付けられているとします。

   ```xml
   ...
   <Import Project="..\..\editorconfig.props" Condition="Exists('..\..\editorconfig.props')" />
   <Import Project="..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.3\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props" Condition="Exists('..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.3\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props')" />
   ...
   ```

4. プロジェクトを再度読み込みます。

> [!NOTE]
> ここで説明する EditorConfig ファイルの任意の共有の場所は、FxCop アナライザーの構成にのみ適用されます。 インデントやコードスタイルなどの他の設定については、EditorConfig ファイルを常にプロジェクトフォルダーまたは親フォルダーに配置する必要があります。

## <a name="option-scopes"></a>オプションスコープ

各オプションは、ルールのカテゴリ (名前付けや設計など)、または特定のルールに対して、すべてのルールに対して構成できます。

### <a name="all-rules"></a>すべてのルール

すべてのルールのオプションを構成するための構文は次のとおりです。

|構文|例|
|-|-|
| dotnet_code_quality.OptionName = OptionValue | `dotnet_code_quality.api_surface = public` |

### <a name="category-of-rules"></a>ルールのカテゴリ

ルールの*カテゴリ*(名前付け、設計、パフォーマンスなど) のオプションを構成するための構文は次のとおりです。

|構文|例|
|-|-|
| dotnet_code_quality.RuleCategory OptionName = OptionValue | `dotnet_code_quality.Naming.api_surface = public` |

### <a name="specific-rule"></a>特定のルール

特定のルールのオプションを構成するための構文は次のとおりです。

|構文|例|
|-|-|
| dotnet_code_quality.RuleId OptionName = OptionValue | `dotnet_code_quality.CA1040.api_surface = public` |

## <a name="see-also"></a>関連項目

- [アナライザーの構成](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)
- [FxCop アナライザー](install-fxcop-analyzers.md)
- [EditorConfig の .NET コーディング規則](../ide/editorconfig-code-style-settings-reference.md)
