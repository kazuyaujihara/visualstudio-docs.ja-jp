---
title: 生成されたコードのコード分析の違反を抑制します。
ms.date: 05/13/2019
ms.topic: conceptual
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6a7990f5e9fa1893d8813b1307ab6a0a7fee46be
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65613571"
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>方法: 生成されたコードに対するコード分析の警告を表示しない

生成されたコードには、マネージ コード コンパイラまたはサードパーティ製のツールで、プロジェクトに追加されるコードが含まれています。 コード分析が生成されたコードで検出する規則違反を確認する場合があります。 ただし、表示し、違反を含むコードを維持することはできません、ためにたくないことを確認します。

**結果生成されたコードを表示しない**プロジェクトのコード分析プロパティ ページでチェック ボックスでは、コード サード パーティのツールによって生成されたコードから分析の警告を表示するかどうかを選択することができます。

> [!NOTE]
> コード分析のエラーおよび警告がフォームやテンプレートで表示される場合、このオプションを使用しても、生成されたコードからこのエラーおよび警告の出力は抑制されません。 フォームまたはテンプレートのソース コードは表示することも保持することもできます。

### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>生成されたコードをプロジェクトで警告を抑制するには

1. プロジェクトを右クリックして**ソリューション エクスプ ローラー**し**プロパティ**します。

2. 選択、**コード分析**タブ。

3. 選択、**結果生成されたコードを表示しない**チェック ボックスをオンします。

> [!NOTE]
> 静的コード分析からの警告を抑制することができますのみ。 現時点からのコード分析の警告を抑制することはできません[アナライザー](roslyn-analyzers-overview.md)します。