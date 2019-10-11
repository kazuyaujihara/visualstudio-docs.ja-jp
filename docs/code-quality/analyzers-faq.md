---
title: EditorConfig とアナライザー
ms.date: 03/11/2019
ms.topic: conceptual
helpviewer_keywords:
- analyzers, faq
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 12e6681490c6c933369d3fef064ec88f240e3a99
ms.sourcegitcommit: b23d73c86ec7720c4cd9a58050860bc559623a3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72172772"
---
# <a name="code-analysis-faq"></a>コード分析に関する FAQ

このページには、Visual Studio での .NET Compiler Platform ベースのコード分析に関してよく寄せられる質問への回答が含まれています。

## <a name="code-analysis-versus-editorconfig"></a>コード分析と EditorConfig

**Q**:コードのスタイルを確認するためにコード分析または EditorConfig を使用する必要がありますか。

**A**:コード分析と EditorConfig ファイルは手動で機能します。 [EditorConfig ファイル](../ide/editorconfig-code-style-settings-reference.md)または [[テキストエディター] オプション](../ide/code-styles-and-code-cleanup.md)ページでコードスタイルを定義する場合、実際には Visual Studio に組み込まれているコードアナライザーを構成します。 EditorConfig ファイルを使用すると、アナライザーの規則を有効または無効にすることができます。また、 [FxCop](configure-fxcop-analyzers.md)アナライザーなどの一部の NuGet アナライザーパッケージを構成することもできます。

## <a name="editorconfig-versus-rule-sets"></a>EditorConfig とルールセット

**Q**:規則セットまたは EditorConfig ファイルを使用してアナライザーを構成する必要がありますか。

**A**:規則セットと EditorConfig ファイルは共存させることができ、どちらもアナライザーの構成に使用できます。 EditorConfig ファイルとルールセットの両方を使用して、ルールを有効または無効にしたり、その重要度を設定したりできます。

ただし、EditorConfig ファイルでは、ルールを構成するための追加の方法が提供されるようになります。

- FxCop アナライザーでは、EditorConfig ファイルを使用して、[分析するコードの種類を定義](fxcop-analyzer-options.md)できます。
- Visual Studio に組み込まれているコードスタイルアナライザーの場合、EditorConfig ファイルを使用すると、コードベースに[適したコードスタイルを定義](../ide/editorconfig-code-style-settings-reference.md)できます。

規則セットと EditorConfig ファイルに加えて、一部のアナライザーは、 C#および VB コンパイラの[追加ファイル](../ide/build-actions.md#build-action-values)としてマークされたテキストファイルを使用して構成されます。

> [!NOTE]
> - EditorConfig ファイルは、Visual Studio 2019 バージョン16.3 以降でルールを有効にし、重要度を設定するためにのみ使用できます。
> - EditorConfig ファイルを使用してレガシ分析を構成することはできませんが、ルールセットはできます。

## <a name="code-analysis-in-ci-builds"></a>CI ビルドでのコード分析

**Q**:.NET Compiler Platform ベースのコード分析は、継続的インテグレーション (CI) ビルドで動作しますか。

**A**:可能。 NuGet パッケージからインストールされたアナライザーでは、これらの規則は[ビルド時に適用](roslyn-analyzers-overview.md#build-errors)されます。これには、CI ビルドの実行中も含まれます。 CI ビルドで使用されるアナライザーは、規則セットと EditorConfig ファイルの両方からの規則の構成を尊重します。 現時点では、Visual Studio に組み込まれているコードアナライザーは NuGet パッケージとして使用できないため、これらの規則は CI ビルドでは適用できません。

## <a name="ide-analyzers-versus-stylecop"></a>IDE アナライザーと StyleCop

**Q**:Visual Studio IDE コードアナライザーと StyleCop アナライザーの違いは何ですか。

**A**:Visual Studio IDE には、コードスタイルと品質の問題の両方を検索する組み込みのアナライザーが含まれています。 これらの規則は、新しく導入された言語機能を使用して、コードの保守性を向上させるのに役立ちます。 IDE アナライザーは、Visual Studio のリリースごとに継続的に更新されます。

[StyleCop アナライザー](https://github.com/DotNetAnalyzers/StyleCopAnalyzers)は、コード内のスタイルの一貫性をチェックする NuGet パッケージとしてインストールされたサードパーティのアナライザーです。 一般に、StyleCop の規則を使用すると、コードベースに対して個人設定を設定できます。

## <a name="code-analyzers-versus-legacy-analysis"></a>コードアナライザーと従来の分析

**Q**:従来の分析と .NET Compiler Platform ベースのコード分析の違いは何ですか。

**A**: .NET Compiler Platform ベースのコード分析では、ソースコードがリアルタイムで分析され、コンパイル中に分析されます。一方、レガシ分析では、ビルドの完了後にバイナリファイルが分析されます。 詳細については、「 [.NET Compiler Platform ベースの分析](roslyn-analyzers-overview.md#source-code-analysis-versus-legacy-analysis)」と「従来の分析と[FxCop アナライザー](fxcop-analyzers-faq.md)に関する FAQ」を参照してください。

## <a name="treat-warnings-as-errors"></a>警告をエラーとして扱う

**Q**:プロジェクトでは、[ビルド] オプションを使用して警告をエラーとして扱います。 レガシ分析からソースコード分析に移行した後、すべてのコード分析警告がエラーとして表示されるようになりました。 これを回避するにはどうすればよいですか。

**A**:コード分析の警告がエラーとして扱われないようにするには、次の手順を実行します。

  1. 次の内容を含む props ファイルを作成します。

     ```xml
     <Project>
        <PropertyGroup>
           <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
        </PropertyGroup>
     </Project>
     ```

  2. .Csproj または .vbproj プロジェクトファイルに行を追加して、前の手順で作成した props ファイルをインポートします。 この行は、FxCop アナライザーの props ファイルをインポートする行の前に配置する必要があります。 たとえば、props ファイルの名前が codeanalysis. props:

     ```xml
     ...
     <Import Project="..\..\codeanalysis.props" Condition="Exists('..\..\codeanalysis.props')" />
     <Import Project="..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.5\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props" Condition="Exists('..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.5\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props')" />
     ...
     ```

## <a name="see-also"></a>関連項目

- [アナライザーの概要](roslyn-analyzers-overview.md)
- [EditorConfig の .NET コーディング規則の設定](../ide/editorconfig-code-style-settings-reference.md)
