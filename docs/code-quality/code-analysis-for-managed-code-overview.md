---
title: マネージ コード用の静的コード分析
ms.date: 03/26/2018
ms.topic: conceptual
f1_keywords:
- vs.projectpropertypages.codeanalysis
helpviewer_keywords:
- code analysis, managed code
- managed code, code analysis
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 38a2bce9e3343c4439eaf033ccfb8d6e58b01baa
ms.sourcegitcommit: 87d7123c09812534b7b08743de4d11d6433eaa13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57222598"
---
# <a name="overview-of-static-code-analysis-for-managed-code-in-visual-studio"></a>Visual Studio でマネージ コード用の静的コード分析の概要

Visual Studio は 2 つの方法でマネージ コードのコード分析を実行することができます: で*FxCop*スタティック分析、マネージ アセンブリの詳細のモダン*Roslyn アナライザー*します。 このトピックでは、FxCop の静的コード分析について説明します。 コード アナライザーを使用してコードの分析の詳細については、[概要の Roslyn アナライザー](../code-quality/roslyn-analyzers-overview.md)を参照してください。

マネージド コードのコード分析を使用すると、マネージド アセンブリを分析し、Microsoft .NET Framework デザイン ガイドラインに規定されたプログラミングやデザインに関する規則違反など、アセンブリに関する情報をレポートとして得ることができます。

分析ツールは、分析中に実行するチェック項目を警告メッセージとして表示します。 警告メッセージは、プログラミングやデザイン上の問題を識別し、可能であれば問題の解決方法を提供します。

> [!NOTE]
> Visual Studio で .NET Core と .NET Standard プロジェクトでは、静的コード分析はサポートされていません。 Msbuild の一部として .NET Core または .NET Standard プロジェクトでコード分析を実行する場合のようなエラーが表示されます**エラー。CA0055:プラットフォームを識別できませんでした\<your.dll >** します。 .NET Core または .NET Standard プロジェクトでコードを分析するには、次のように使用します。 [Roslyn アナライザー](../code-quality/roslyn-analyzers-overview.md)代わりにします。

## <a name="ide-integrated-development-environment-integration"></a>IDE (統合開発環境) の統合

手動または自動では、プロジェクトでコード分析を実行できます。

プロジェクトをビルドするたびにコード分析を実行する選択**ビルドに対するコード分析を有効にする**プロジェクトのプロパティ ページ。 詳細については、「[方法 :自動コード分析を有効/無効にする](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)」を参照してください。

プロジェクトに手動でコード分析を実行する、メニュー バーから選択**分析** > **コード分析を実行** > **でコード分析を実行\<プロジェクト>** します。

## <a name="rule-sets"></a>規則セット

マネージド コード用のコード分析規則は、[規則セット](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)にグループ化されています。 Microsoft 標準の規則セットのいずれかを使用することもできます[カスタム規則セットを作成](../code-quality/how-to-create-a-custom-rule-set.md)を特定のニーズを満たすためにします。

## <a name="suppress-warnings"></a>警告を表示しない

警告が適用されないことを示すと役に立つことがよくあります。 これによって、開発者や、そのコードを後でレビューする担当者は、その警告が既に調査済みであり、抑制されるのかまたは無視されるのかがわかります。

警告のソース内抑制は、カスタム属性によって実装されます。 警告を抑制するには、次の例のように、属性 `SuppressMessage` をソース コードに追加します。

```csharp
[System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]
Public class MyClass
{
   // code
}
```

詳細については、[警告を抑制する](../code-quality/in-source-suppression-overview.md)を参照してください。

> [!NOTE]
> Visual Studio 2017 または Visual Studio 2019 にプロジェクトを移行する場合にコード分析の警告の数が多いを突然直面する可能性があります。 場合は、警告を修正し、すぐに生産性を向上する準備ができて、*ベースライン*プロジェクトの分析の状態。 **分析**メニューの**コード分析を実行し、アクティブな懸案事項の抑制**です。

## <a name="run-code-analysis-as-part-of-check-in-policy"></a>チェックイン ポリシーの一部としてのコード分析の実行

組織的な取り決めとして、チェックインされるすべてのコードが、特定のポリシーを満たしていることが必要な場合があります。 たとえば、次のようなポリシーが考えられます。

- チェックインされているコードでは、ビルド エラーはありません。

- コード分析は、最新のビルドの一部として実行されます。

これは、チェックイン ポリシーを指定することにより実現できます。 詳細については、[プロジェクトでは、チェックイン ポリシーによるコード品質の向上](../code-quality/how-to-create-or-update-standard-code-analysis-check-in-policies.md)を参照してください。

## <a name="team-build-integration"></a>チーム ビルドの統合

ビルド システムの統合機能を使用すると、分析ツールをビルド プロセスの一環として実行できます。 詳細については、「[Azure Pipelines](/azure/devops/pipelines/index?view=vsts)」を参照してください。

## <a name="see-also"></a>関連項目

- [Roslyn アナライザーの概要](../code-quality/roslyn-analyzers-overview.md)
- [規則セットを使用したコード分析規則のグループ化](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [方法: 自動コード分析を有効/無効にする](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)
