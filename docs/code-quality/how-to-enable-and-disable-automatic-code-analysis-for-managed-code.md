---
title: コード分析を有効または無効にする
ms.date: 10/25/2018
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ec0a8a3f04830115d343fcef611cfbd338163395
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551039"
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>方法: マネージコードの自動コード分析を有効または無効にする

マネージコードプロジェクトの各ビルドの後に実行するように (静的) コード分析を構成できます。 デバッグやリリースなど、ビルド構成ごとに異なるコード分析プロパティを設定できます。

この記事は、[コードアナライザー](roslyn-analyzers-overview.md)を使用した、ライブコード分析ではなく、レガシ分析にのみ適用されます。

## <a name="to-enable-or-disable-automatic-code-analysis"></a>自動コード分析を有効または無効にするには

1. **ソリューション エクスプ ローラー** で、プロジェクトを右クリックし、**プロパティ**を選択します。

1. プロジェクトの プロパティ ダイアログボックスで、**コード分析** タブを選択します。

   > [!TIP]
   > .NET Core や .NET Standard アプリケーションなどの新しいプロジェクトの種類には、 **[コード分析]** タブがありません。レガシ分析は、これらの種類のプロジェクトでは使用できませんが、 [.NET Compiler Platform ベースのコードアナライザー](roslyn-analyzers-overview.md)を使用してライブコード分析を行うことができます。 コードアナライザーからの警告を非表示にするには、この記事の最後にあるメモを参照してください。

1. **プラットフォーム** の **構成およびターゲット プラットフォーム** でビルドの種類を指定します。

1. 自動コード分析を有効または無効にするには、**ビルドに対するコード分析を有効にする**のチェック ボックスをオンまたはオフします。

> [!NOTE]
> **[ビルドでコード分析を有効にする]** チェックボックスは、レガシ分析にのみ影響します。 [.NET Compiler Platform ベースのコードアナライザー](roslyn-analyzers-overview.md)には影響しません。 NuGet パッケージとしてインストールした場合は、常にビルドで実行されます。 **エラー一覧**からアナライザーのエラーをクリアする場合は、メニューバーの [**実行コード分析を** **分析** > し、アクティブな問題を抑制する] を選択して、現在のすべての違反を抑制することができます。 詳細については、「[違反の抑制](use-roslyn-analyzers.md#suppress-violations)」を参照してください。
