---
title: コード分析を使用してマネージ コードの品質の分析 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis,managed code
- managed code analyis
ms.assetid: 68510a55-da51-4381-81a5-0feba76b8b4f
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5d8740b79b026ade7f3da19aa4a89cacd94df17d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973919"
---
# <a name="analyzing-managed-code-quality-by-using-code-analysis"></a>コード分析を使用したマネージド コードの品質の分析
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio のコード分析ツールを使用すると、安全ではないデータ アクセス、使用法違反、デザイン上の問題など、コード内の潜在的な問題を検出できます。 コード分析の動作環境は、.NET Framework、ネイティブ (C と C++)、およびデータベース アプリケーションです。 マネージ コードのコード分析で規則を整理する*ルール セット*を対象とするコーディングの問題を特定します。  
  
## <a name="common-tasks"></a>よく使う機能  
  
|よく使う機能|関連する参照先|  
|------------------|------------------------|  
|**ハンズオン プラクティスを取得します。** 単純な .NET Framework アプリケーションの欠陥を修正することによって、コード分析の基本を説明します。|-   [チュートリアル: マネージド コードの分析によるコード障害の検出](../code-quality/walkthrough-analyzing-managed-code-for-code-defects.md)|  
|**プロジェクトのコード分析を構成します。** マネージ コードの規則は、セキュリティ、デザインなど、特定の分野を対象とする規則セットに編成されます。 Microsoft の標準の規則セットの 1 つを使用することも、独自のセットを作成することもできます。|-   [マネージ コードの概要のコード分析](../code-quality/code-analysis-for-managed-code-overview.md)<br />-   [コード分析規則のグループに規則を使用して設定します。](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)<br />-   [SuppressMessage 属性を使用して警告を抑制します。](../code-quality/suppress-warnings-by-using-the-suppressmessage-attribute.md)|  
|**コード分析を実行します。** プロジェクトの構成がビルドされるたびに自動的に実行されるコード分析を指定して、プロジェクトでコード分析を手動で実行することができます。|-   [方法: 自動コード分析を有効/無効にする](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)<br />-   [方法: コード分析を手動で実行します。](../code-quality/how-to-run-code-analysis-manually-for-managed-code.md)|  
|**コード分析の結果を分析するには。** コード分析の警告とエラーは、コード分析 ウィンドウに表示されます。 警告またはエラーのタイトルを選択すると、警告に関する追加情報を表示し、規則を発動したソース コード行を表示および強調表示することができます。 警告 ID を選択すると、問題の解決方法に関する情報と例が含まれた、MSDN ライブラリの詳細情報を表示できます。|-   [方法: マネージ コードの障害を表示します。](../code-quality/how-to-view-managed-code-defects.md)<br />-   [マネージ コードの警告のコード分析](../code-quality/code-analysis-for-managed-code-warnings.md)<br />-   [警告を checkid 別](../code-quality/code-analysis-warnings-for-managed-code-by-checkid.md)<br />-   [匿名メソッドとコード分析](../code-quality/anonymous-methods-and-code-analysis.md)|  
|**コード分析を開発ライフ サイクルに統合します。** チェックイン ポリシーで[!INCLUDE[esprscc](../includes/esprscc-md.md)]開発チームが有効にするすべてのコードのチェックインがあるかどうかを確認するコード分析標準の共通セットに対応します。 コード分析規則違反の作業項目は、[エラー一覧] ウィンドウで簡単な手順により作成できます。|-   [チーム プロジェクト チェックイン ポリシーによるコード品質の向上](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)<br />-   [方法: チーム プロジェクト チェックイン ポリシーとコード プロジェクト規則セットを同期させる](../code-quality/how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)<br />-   [方法: マネージ コードの障害に対する作業項目を作成します。](../code-quality/how-to-create-a-work-item-for-a-managed-code-defect.md)|
