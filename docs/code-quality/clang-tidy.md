---
title: Visual Studio での Clang-Tidy の使用
ms.date: 10/04/2019
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.clangtidy
author: frozenpandaman
ms.author: efessler
ms.workload:
- cplusplus
ms.openlocfilehash: 430d0e271f83332f7163c9c0c947f96756ca7a7d
ms.sourcegitcommit: e95dd8cedcd180e0bce6a75c86cf861757918290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72165141"
---
# <a name="using-clang-tidy-in-visual-studio"></a>Visual Studio での Clang-Tidy の使用

コード分析では、Clang または MSVC ツールセットを使用するかどうかにかかわらず、MSBuild プロジェクトと CMake プロジェクトの両方に対して[clang-Tidy が](https://clang.llvm.org/extra/clang-tidy/)ネイティブでサポートされます。 Clang-Tidy チェックは、バックグラウンドコード分析の一部として実行でき、エディター内警告 (波線) として表示され、エラー一覧に表示されます。

Clang-Tidy を使用するには、"C++ clang Tools for Windows" コンポーネントが Visual Studio インストーラー経由でインストールされている必要があります。

Clang-Tidy は、MSBuild と CMake の両方で使用できる LLVM/clang-cl ツールセットを使用する場合の既定の分析ツールです。 MSVC ツールセットを使用しているときに、標準のコード分析エクスペリエンスを同時に実行するように構成することもできます。clang-cl ツールセットを使用している場合、Microsoft コード分析は使用できません。

Clang-コンパイルが成功した後に実行されます。場合によっては、ソースコードエラーを解決して Clang-Tidy の結果を取得する必要があります。


## <a name="msbuild"></a>MSBuild

プロジェクトプロパティウィンドウの **[コード分析]**  >  **[全般]** ページで、コード分析とビルドの両方の一部として実行するように clang-Tidy を構成できます。 ツールを構成するオプションについては、「Clang-Tidy サブメニュー」を参照してください。

詳細については、「[方法 :C/C++ Projects @ No__t のコード分析プロパティを設定します。

## <a name="cmake"></a>CMake

CMake プロジェクトでは、`CMakeSettings.json` で Clang のチェックを構成できます。 開いたら、CMake プロジェクト設定エディターの右上隅にある [JSON の編集] をクリックします。 次のキーが認識されます。

- `enableMicrosoftCodeAnalysis`:Microsoft コード分析を有効にします
- `enableClangTidyCodeAnalysis`:Clang-Tidy 分析を有効にします
- `clangTidyChecks`:Clang-構成。コンマ区切りのリストとして指定します。つまり、有効または無効にします。

"Enable" オプションのいずれも指定されていない場合、Visual Studio は、使用されているプラットフォームツールセットと一致する分析ツールを選択します。

## <a name="warning-display"></a>警告の表示

Clang-Tidy を実行すると、エラー一覧に警告が表示されます。また、コードの関連するセクションの下にエディター上の波線が表示されます。 エラー一覧の [カテゴリ] 列を使用して、Clang-Tidy 警告を並べ替えて整理します。 [**ツール** >  の**オプション**] の [コード分析の波線を無効にする] 設定を切り替えることによって、エディター内の警告を構成できます。

## <a name="clang-tidy-configuration"></a>Clang-Tidy 構成

Clang-tidy**チェック**オプションを使用して、Visual Studio 内で clang-tidy が実行されるかどうかをチェックするように構成できます。 この入力は、ツールの **--チェック**引数に提供されます。 追加の構成は、カスタムの**clang-tidy**ファイルに含めることができます。 詳細については、 [LLVM.org にある Clang-Tidy のドキュメント](https://clang.llvm.org/extra/clang-tidy/)を参照してください。

## <a name="see-also"></a>関連項目

- [Clang/LLVM の MSBuild プロジェクトのサポート](https://aka.ms/cpp/clangmsbuild)
- [Clang/LLVM での CMake プロジェクトのサポート](https://aka.ms/cpp/clangcmake)
