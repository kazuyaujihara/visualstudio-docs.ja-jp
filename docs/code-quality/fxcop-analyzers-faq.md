---
title: FxCop コード分析および FxCop アナライザー
ms.date: 09/06/2018
ms.topic: conceptual
helpviewer_keywords:
- code analysis FAQ
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 277155bdab713ec12daa380fc2721a31b5d932a2
ms.sourcegitcommit: 7825d4163e52d724e59f6c0da209af5fbef673f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72000119"
---
# <a name="frequently-asked-questions-about-fxcop-and-fxcop-analyzers"></a>FxCop および FxCop アナライザーに関してよく寄せられる質問

従来の FxCop と FxCop アナライザー間の違いは、少し理解しにくい場合があります。 この記事は、ユーザーの方々がお持ちの質問を解決することを意図しています。

## <a name="whats-the-difference-between-legacy-fxcop-and-fxcop-analyzers"></a>従来の FxCop と FxCop アナライザー間の違いは何ですか?

従来の FxCop は、コンパイル済みのアセンブリ上でビルド後の分析を実行します。 これは、**FxCopCmd.exe** という別の実行可能ファイルとして実行されます。 FxCopCmd.exe はコンパイル済みのアセンブリを読み込み、コード分析を実行し、結果 (または*診断*) を報告します。

FxCop アナライザーは .NET Compiler Platform ("Roslyn") に基づいています。 これは、ユーザーがプロジェクトまたはソリューションで参照する [NuGet パッケージとしてインストール](install-fxcop-analyzers.md#nuget-package)します。 FxCop アナライザーは、コンパイラーの実行中にソースコードに基づく分析を実行します。 FxCop アナライザーは、**csc.exe** または **vbc.exe** のコンパイラーのプロセス内にホストされ、プロジェクトの構築時に分析を実行します。 アナライザーの結果は、コンパイラーの結果と共に報告されます。

> [!NOTE]
> [FxCop アナライザーは、Visual Studio の拡張機能としてインストールする](install-fxcop-analyzers.md#vsix)ことも可能です。 この場合、コード エディターに入力を行うとアナライザーが実行されます。ビルド時には実行されません。 継続的インテグレーション (CI) の一環として FxCop を実行する場合、代わりに NuGet パッケージとしてインストールします。

## <a name="does-the-run-code-analysis-command-run-fxcop-analyzers"></a>[コード分析の実行] コマンドで FxCop アナライザーを実行できますか?

No. [@No__t の**分析**] を選択すると、**コード分析が実行**され、従来の分析が実行されます。 **[コード分析の実行]** は、Roslyn ベースの FxCop アナライザーを含む Roslyn ベースのアナライザーには何の影響もありません。

## <a name="does-the-runcodeanalysis-msbuild-project-property-run-analyzers"></a>RunCodeAnalysis msbuild プロジェクト プロパティはアナライザーを実行しますか?

No. (たとえば *.csproj* の) プロジェクト ファイル内の **RunCodeAnalysis** プロパティは、従来の FxCop を実行するためのみに使用します。 これは、**FxCopCmd.exe** を起動するビルド後の msbuild タスクを実行します。 これは、Visual Studio で **[分析]**  >  **[コード分析の実行]** を選択するのと同等です。

## <a name="so-how-do-i-run-fxcop-analyzers-then"></a>では FxCop アナライザーはどのように実行するのですか?

FxCop アナライザーを実行するには、まずそれ用に [NuGet パッケージをインストール](install-fxcop-analyzers.md)します。 次いでプロジェクトまたはソリューションを Visual Studio または msbuild を使用してビルドします。 FxCop アナライザーが生成する警告やエラーは、 **[エラー一覧]** またはコマンド ウィンドウに表示されます。

## <a name="i-get-warning-ca0507-even-after-ive-installed-the-fxcop-analyzers-nuget-package"></a>FxCop アナライザーの NuGet パッケージをインストールした後でも警告 CA0507 を取得する

FxCop アナライザーがインストールされていても、警告が引き続き表示される場合は **、ビルド中に実行される fxcop アナライザーを優先して、"コード分析の実行" が非推奨**となりました。プロジェクトで**runcodeanalysis** msbuild プロパティを設定する必要がある場合があります。 [ファイル](../ide/solutions-and-projects-in-visual-studio.md#project-file)を**false**にします。 それ以外の場合、レガシ分析は各ビルドの後に実行されます。

```xml
<RunCodeAnalysis>false</RunCodeAnalysis>
```

## <a name="which-rules-have-been-ported-to-fxcop-analyzers"></a>FxCop アナライザーに移植されたルール

[Fxcop アナライザー](install-fxcop-analyzers.md)に移植された従来の分析ルールの詳細については、「 [fxcop rule port status](fxcop-rule-port-status.md)」を参照してください。

## <a name="code-analysis-warnings-are-treated-as-errors"></a>コード分析の警告はエラーとして扱われます

プロジェクトでビルドオプションを使用して警告をエラーとして扱う場合、FxCop アナライザーの警告がエラーとして表示されることがあります。 コード分析の警告がエラーとして扱われないようにするには、「[コード分析](../code-quality/analyzers-faq.md#treat-warnings-as-errors)に関する FAQ」の手順に従います。

## <a name="see-also"></a>関連項目

- [.NET Compiler Platform アナライザーの概要](roslyn-analyzers-overview.md)
- [アナライザーの概要](fxcop-analyzers.yml)
- [FxCop アナライザーのインストール](install-fxcop-analyzers.md)
