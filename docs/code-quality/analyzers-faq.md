---
title: EditorConfig アナライザーとの比較
ms.date: 03/11/2019
ms.topic: conceptual
helpviewer_keywords:
- analyzers, faq
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bec9296f15c48cf3b327c78cd0ce7d57adafa002
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57874686"
---
# <a name="analyzers-faq"></a>アナライザーの FAQ

このページには、Visual Studio で Roslyn アナライザーについてよく寄せられる質問に対する回答が含まれています。

## <a name="roslyn-analyzers-versus-editorconfig"></a>.Editorconfig と Roslyn アナライザー

**Q**:コード スタイルの Roslyn アナライザーまたは .editorconfig を使って必要がありますか

**A**:Roslyn アナライザーと .editorconfig ファイルは、手の形密接に機能します。 コード スタイルを定義するとき[.editorconfig ファイルで](../ide/editorconfig-code-style-settings-reference.md)か、または、[テキスト エディター オプション](../ide/code-styles-and-quick-actions.md) ページで、Visual Studio に組み込まれている Roslyn アナライザー実際に構成しています。 EditorConfig ファイルがなど、一部のサード パーティ製のアナライザー パッケージを構成することもでき[FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="editorconfig-versus-rule-sets"></a>EditorConfig 規則セットとの比較

**Q**:規則セットまたは .editorconfig ファイルを使用して、アナライザーを構成する必要がありますか。

**A**:ルール セットおよび .editorconfig ファイルは、アナライザーを構成する方法を相互に排他的です。 これらを共存させることができます。 [ルール セット](analyzer-rule-sets.md)を有効にしてルールを無効にして、重大度を設定することができます。 EditorConfig ファイルでは、その他の規則を構成する方法を提供します。 FxCop アナライザーの場合は、.editorconfig ファイルを使用する[を分析するコードの種類を定義する](fxcop-analyzer-options.md)します。 Visual Studio に組み込まれているアナライザーの .editorconfig ファイルを使用する[優先コード スタイル定義](../ide/editorconfig-code-style-settings-reference.md)コードベースにします。

としてマークされているテキスト ファイルを使用してルール セットおよび .editorconfig ファイルでは、だけでなく、サードパーティのいくつかのアナライザーが構成されている[追加ファイル](../ide/build-actions.md#build-action-values)のC#と VB コンパイラ。

> [!NOTE]
> 規則セットのことができますが、静的コード分析の規則を構成する EditorConfig ファイルを使用できません。

## <a name="analyzers-in-ci-builds"></a>CI ビルドでアナライザー

**Q**:アナライザーは継続的インテグレーション (CI) ビルドで機能しますか。

**A**:はい。 これらの規則は、アナライザーの NuGet パッケージからインストールされている場合、[ビルド時に適用される](roslyn-analyzers-overview.md#build-errors)CI ビルド中に含め、します。 アナライザーの両方から CI ビルドに関してルールの構成で使用される[ルール セット](analyzer-rule-sets.md)と[.editorconfig ファイル](configure-fxcop-analyzers.md)します。 現在、Visual Studio に組み込まれているコード アナライザーは、NuGet パッケージとして使用できません、ためこれらの規則は CI ビルドで強制はありません。

## <a name="ide-analyzers-versus-stylecop"></a>StyleCop ではなく IDE アナライザー

**Q**:Visual Studio IDE のコード アナライザーと StyleCop アナライザーの違いは何ですか。

**A**:Visual Studio IDE には、両方のコード スタイルと品質の問題を検索する組み込みのアナライザーが含まれています。 これらの規則に役立つ、導入するいるし、コードの保守容易性を向上させる新しい言語機能を使用します。 IDE のアナライザーは絶えず更新されている Visual Studio のリリースごとにします。

[StyleCop アナライザー](https://github.com/DotNetAnalyzers/StyleCopAnalyzers)は NuGet パッケージとしてインストールされているサード パーティ製アナライザー、コード スタイルの一貫性をチェックします。 一般に、StyleCop のルールを 1 つのスタイルを推奨することがなくコードの個人設定を基本設定を使用できます。

## <a name="analyzers-versus-static-code-analysis"></a>静的コード分析とアナライザー

**Q**:アナライザーと静的コード分析の違いは何ですか。

**A**:アナライザーは、静的コード分析は、ビルドが完了した後にバイナリ ファイルを分析し、リアルタイムでは、コンパイル時にソース コードを分析します。 詳細については、[静的コード分析と Roslyn アナライザー](roslyn-analyzers-overview.md#roslyn-analyzers-vs-static-code-analysis)と[FxCop アナライザー FAQ](fxcop-analyzers-faq.md)を参照してください。

## <a name="see-also"></a>関連項目

- [アナライザーの概要](roslyn-analyzers-overview.md)
- [EditorConfig の .NET コーディング規則の設定](../ide/editorconfig-code-style-settings-reference.md)