---
title: コード メトリックに関する問題のトラブルシューティング | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: troubleshooting
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1567715a8f944eb10c2728caa9fc1edd43beda8e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62580585"
---
# <a name="troubleshooting-code-metrics-issues"></a>コード メトリックに関する問題のトラブルシューティング
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

コード メトリックを収集するときに、次に示す問題が発生する場合があります。  
  
- [Visual Studio 2010 のコードの複雑度の計算における変更点](#Changes_in_Visual_Studio_2010_code_complexity_calculations)  
  
## <a name="Changes_in_Visual_Studio_2010_code_complexity_calculations"></a>Visual Studio 2010 のコードの複雑度の計算における変更点  
 次のような状況では、同じ関数について [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] で計算したコードの複雑度のメトリックと旧バージョンの [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] で計算したメトリックとが異なる場合があります。  
  
- 関数に 1 つ以上の catch ブロックが含まれている。 以前のバージョンの [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] では、catch ブロックが計算に含まれていませんでした。 [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] では、各 catch ブロックの複雑度が関数の複雑度に加算されます。  
  
- 関数に switch (VB の場合は Select Case) ステートメントが含まれている。 [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] と旧バージョンの間のコンパイラの相違点により、case のフォールスルーを含んでいる一部の switch ステートメントに対して、異なる MSIL コードが生成される場合があります。  
  
## <a name="see-also"></a>関連項目  
 [マネージド コードの複雑さと保守性の測定](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)
