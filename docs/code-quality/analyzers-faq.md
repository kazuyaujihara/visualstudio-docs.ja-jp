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
ms.openlocfilehash: ae41d9ac30567a32780af422c3af1e2b0d6a63ae
ms.sourcegitcommit: b761a4a457646d04adfda510c8837734ee4d8f17
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929771"
---
# <a name="code-analysis-faq"></a>コード分析に関する FAQ

このページには、Visual Studio での .NET Compiler Platform ベースのコード分析に関してよく寄せられる質問への回答が含まれています。

## <a name="code-analysis-versus-editorconfig"></a>コード分析と EditorConfig

**Q**:コードのスタイルを確認するためにコード分析または EditorConfig を使用する必要がありますか。

**A**:コード分析と editorconfig ファイルは手動で機能します。 [Editorconfig ファイル](../ide/editorconfig-code-style-settings-reference.md)または [[テキストエディター] オプション](../ide/code-styles-and-code-cleanup.md)ページでコードスタイルを定義する場合、実際には、Visual Studio に組み込まれているコードアナライザーを構成します。 EditorConfig ファイルを使用して、 [FxCop](configure-fxcop-analyzers.md)アナライザーなどの一部の NuGet アナライザーパッケージを構成することもできます。

## <a name="editorconfig-versus-rule-sets"></a>EditorConfig とルールセット

**Q**:規則セットまたは editorconfig ファイルを使用してアナライザーを構成する必要がありますか。

**A**:規則セットと editorconfig ファイルは、アナライザーを構成するための相互に排他的な方法です。 共存させることができます。 規則[セット](analyzer-rule-sets.md)を使用すると、規則を有効または無効にし、その重要度を設定できます。 EditorConfig ファイルには、ルールを構成するための他の方法が用意されています。 FxCop アナライザーでは、editorconfig ファイルを使用して、[分析するコードの種類を定義](fxcop-analyzer-options.md)できます。 Visual Studio に組み込まれているアナライザーの場合、editorconfig ファイルを使用すると、コードベースに適した[コードスタイルを定義](../ide/editorconfig-code-style-settings-reference.md)できます。

規則セットと editorconfig ファイルに加えて、一部のアナライザーは、 C#および VB コンパイラの[追加ファイル](../ide/build-actions.md#build-action-values)としてマークされたテキストファイルを使用して構成されます。

> [!NOTE]
> EditorConfig ファイルを使用してレガシ分析を構成することはできませんが、ルールセットはできます。

## <a name="code-analysis-in-ci-builds"></a>CI ビルドでのコード分析

**Q**:.NET Compiler Platform ベースのコード分析は、継続的インテグレーション (CI) ビルドで動作しますか。

**A**:はい。 NuGet パッケージからインストールされたアナライザーでは、これらの規則は[ビルド時に適用](roslyn-analyzers-overview.md#build-errors)されます。これには、CI ビルドの実行中も含まれます。 CI ビルドで使用されるアナライザーは、[規則セット](analyzer-rule-sets.md)と[editorconfig ファイル](configure-fxcop-analyzers.md)の両方からの規則の構成を尊重します。 現時点では、Visual Studio に組み込まれているコードアナライザーは NuGet パッケージとして使用できないため、これらの規則は CI ビルドでは適用できません。

## <a name="ide-analyzers-versus-stylecop"></a>IDE アナライザーと StyleCop

**Q**:Visual Studio IDE コードアナライザーと StyleCop アナライザーの違いは何ですか。

**A**:Visual Studio IDE には、コードスタイルと品質の問題の両方を検索する組み込みのアナライザーが含まれています。 これらの規則は、新しく導入された言語機能を使用して、コードの保守性を向上させるのに役立ちます。 IDE アナライザーは、Visual Studio のリリースごとに継続的に更新されます。

[StyleCop アナライザー](https://github.com/DotNetAnalyzers/StyleCopAnalyzers)は、コード内のスタイルの一貫性をチェックする NuGet パッケージとしてインストールされたサードパーティのアナライザーです。 一般に、StyleCop の規則を使用すると、コードベースに対して個人設定を設定できます。

## <a name="code-analyzers-versus-legacy-analysis"></a>コードアナライザーと従来の分析

**Q**:従来の分析と .NET Compiler Platform ベースのコード分析の違いは何ですか。

**A**: .NET Compiler Platform ベースのコード分析では、ソースコードがリアルタイムで分析され、コンパイル中に分析されます。一方、レガシ分析では、ビルドの完了後にバイナリファイルが分析されます。 詳細については、「 [.NET Compiler Platform ベースの分析](roslyn-analyzers-overview.md#net-compiler-platform-based-analysis-versus-legacy-analysis)」と「従来の分析と[FxCop アナライザー](fxcop-analyzers-faq.md)に関する FAQ」を参照してください。

## <a name="see-also"></a>関連項目

- [アナライザーの概要](roslyn-analyzers-overview.md)
- [EditorConfig の .NET コーディング規則の設定](../ide/editorconfig-code-style-settings-reference.md)