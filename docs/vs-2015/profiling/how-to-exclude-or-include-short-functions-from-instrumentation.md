---
title: '方法 : インストルメンテーションで短い関数を除外または含める | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, instrument events
- profiling tools, include short functions
- profiling tools, exclude short functions
ms.assetid: eaeead79-aafe-4490-86ff-6ed4cad9c15f
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d37984b6535e353053ba6ee71090797e4ce119d3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54801662"
---
# <a name="how-to-exclude-or-include-short-functions-from-instrumentation"></a>方法 : インストルメンテーションで短い関数を除外または含める
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

既定では、プロファイリング ツールは*小規模関数*をインストルメンテーションから除外します。 小規模関数とは、関数の呼び出しを行わない短い関数のことです。 小規模関数を除外すると、インストルメンテーション オーバーヘッドが軽減するため、インストルメンテーションの速度が向上します。 また、小規模関数の除外によりパフォーマンス プロファイル データ ファイル (.vsp) のサイズが小さくなるため、分析に要する時間が短縮されます。 小規模関数が除外されると、その親関数の排他時間と包括時間に対して、小規模関数に費やされる時間が除外されます。 次に、インストルメンテーションで小規模関数を除外または含める手順について説明します。  
  
### <a name="to-exclude-or-include-short-functions-from-instrumentation"></a>インストルメンテーションで短い関数を除外または含めるには  
  
1.  **パフォーマンス エクスプローラー**で、**パフォーマンス セッション**を選択します。次に、右クリックして **[プロパティ]** を選択します。  
  
     **[プロパティ ページ]** ダイアログ ボックスが表示されます。  
  
2.  **[プロパティ ページ]** で、**[インストルメンテーション]** プロパティをクリックします。  
  
3.  インストルメンテーションから短い関数を除外するには、**[短い関数をインストルメンテーションから除外]** をオンにします。 これは、既定の設定です。  
  
     - または -  
  
     インストルメンテーションに短い関数を含めるには、**[短い関数をインストルメンテーションから除外]** をオフにします。  
  
4.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>関連項目  
 [データ コレクションの制御](../profiling/controlling-data-collection.md)   
 [パフォーマンス セッションのプロパティ](../profiling/performance-session-properties.md)
