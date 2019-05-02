---
title: C/C++ のコード分析の概要
ms.date: 04/28/2018
ms.topic: conceptual
helpviewer_keywords:
- annotations, code analysis
- build integration, code analysis
- C/C++ code analysis
- IDE, code analysis
- pragma directive, code analysis
- code analysis, C/C++
- code analysis tool
- command line, code analysis
- C++, code analysis
- check-in policies, code analysis
- '#pragma directives, code analysis'
- C, code analysis
ms.assetid: 81f0c9e8-f471-4de5-aac4-99db336a8809
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: 07ba2c64be0af987b82c870b89d3451b5d48d28f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62540828"
---
# <a name="code-analysis-for-cc-overview"></a>C/C++ のコード分析の概要

C/C++ コード分析ツールは、C/C++ ソース コードの障害に関する情報を提供します。 このツールで報告される一般的なコーディング エラーとして、バッファー オーバーラン、初期化されていないメモリ、Null ポインターの逆参照、メモリ リーク、リソース リークなどがあります。 ツールは、に対してチェックを実行できることも、 [C++ Core Guidelines](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)します。

## <a name="ide-integrated-development-environment-integration"></a>IDE (統合開発環境) の統合

コード分析ツールは、Visual Studio IDE 内で完全に統合されています。

ビルド プロセス中は、ソース コードに対して生成された警告がエラー一覧に表示されます。 警告の原因となったソース コードに移動して、問題の原因と考えられる解決策に関する追加情報を表示できます。

## <a name="command-line-support"></a>コマンド ライン サポート

次の例に示すように、コマンドラインからの分析ツールを使用することもできます。

```cmd
C:\>cl /analyze Sample.cpp
```

**Visual Studio 2017 バージョン 15.7 以降**CMake を含むすべてのビルド システムでコマンド ライン ツールを実行することができます。

## <a name="pragma-support"></a>#pragma サポート

使用することができます、`#pragma`ディレクティブは警告をエラーとして扱う; 有効または警告を無効にする個々 の行のコードの警告を非表示にします。 詳細については、「[方法 :C と C++ プロジェクトのコード分析プロパティを設定](how-to-set-code-analysis-properties-for-c-cpp-projects.md)します。

## <a name="annotation-support"></a>注釈のサポート

注釈によってコード分析の精度が向上します。 注釈には、関数のパラメーターと戻り値の型について、事前および事後の状態に関する追加情報を指定します。 詳細については、「[方法 :__analysis_assume を使用して追加のコード情報を指定する](../code-quality/how-to-specify-additional-code-information-by-using-analysis-assume.md)」を参照してください。

## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>チェックイン ポリシーの一部としての分析ツールの実行

チェックインされるすべてのソース コードが、特定のポリシーを満たしていることが必要な場合があります。 具体的には、最新のローカル ビルドのステップとして分析が実行されたことを確認する必要があります。 コード分析チェックイン ポリシーを有効にする方法の詳細については、「[コード分析を用いたチェックイン ポリシーの作成と使用](../code-quality/how-to-create-or-update-standard-code-analysis-check-in-policies.md)」を参照してください。

## <a name="team-build-integration"></a>チーム ビルドの統合

ビルド システムの統合機能を使用すると、コード分析ツールを [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] ビルド プロセスのステップとして実行できます。 詳細については、「[Azure Pipelines](/azure/devops/pipelines/index?view=vsts)」を参照してください。

## <a name="see-also"></a>関連項目

- [クイック スタート:C/C++ のコード分析](quick-start-code-analysis-for-c-cpp.md)
- [チュートリアル: C/C++ コードの分析による障害の](walkthrough-analyzing-c-cpp-code-for-defects.md)
- [C/C++ コードの警告に対応するコードの分析](code-analysis-for-c-cpp-warnings.md)
- [C++ Core ガイドライン チェッカーの使用](using-the-cpp-core-guidelines-checkers.md)
- [C++ Core ガイドライン チェッカーの参照](code-analysis-for-cpp-corecheck.md)
- [規則セットを使用して実行対象の C++ 規則を指定する](using-rule-sets-to-specify-the-cpp-rules-to-run.md)
- [コード分析ツールを使用して、ドライバーの品質を分析します。](/windows-hardware/drivers/develop/analyzing-driver-quality-by-using-code-analysis-tools)
- [Code Analysis for Drivers の警告](/windows-hardware/drivers/devtest/prefast-for-drivers-warnings)
