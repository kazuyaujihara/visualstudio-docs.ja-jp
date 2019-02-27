---
title: CPU 使用状況グラフ | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.cpu.graph
helpviewer_keywords:
- CPU Utilization GraphConcurrency Visualizer, CPU Utilization Graph
ms.assetid: 5332fd38-622d-47a3-874f-8c2fd7a30f95
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 42995305b76acdda7f24fb7a45f717c9f2c174a2
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56631251"
---
# <a name="cpu-utilization-graph"></a>CPU 使用状況グラフ
CPU 使用状況グラフは、時間経過に対するアプリの使用状況のレベルを示します。 X 軸はトレースの期間を表し、Y 軸はシステム上の論理コアの数を表します。 任意の時点にどのコアがアクティブかは表示されません。 たとえば、2 つのコアが特定の期間それぞれ最大利用可能時間の 50% 実行されている場合、このビューには使用されている 1 つの論理コアが表示されます。

## <a name="cpu-utilization-graph-colors"></a>CPU 使用状況グラフの色

-   緑は、現在のプロセスによるシステムの論理コアの使用状況を示します。

-   明るいグレーは、システム上の他のプロセスによる論理コアの使用状況を示します。 CPU グラフの明るいグレーの割合が高い場合は、他のプロセスによってシステムの負荷が高く、自分のプロセスよりそれらが優先されていることを示します。 他のプロセスによる論理コアの消費量を減らすには、システム上で実行される他のプロセスの数を減らします。

-   濃いグレーは、システム プロセスによる論理コアの使用量を示します。 これを直接制御することはできませんが、プロセスが論理コアを使用できるかどうかに影響する場合があるので、いつ発生するのかを知っておくと役に立ちます。

-   白は、システム上の未使用の論理コアを使用できるかどうかを示します。 これらのコアは、並列処理の機会があれば、プロセスで使用できます。

## <a name="see-also"></a>関連項目
- [使用状況ビュー](../profiling/utilization-view.md)
- [平均 CPU 使用状況](../profiling/average-cpu-utilization.md)