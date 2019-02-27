---
title: GPU アクティビティ グラフ | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.cpu.graph.gpu
ms.assetid: d7c769af-95fb-49a3-b5ab-deafecee46fa
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5734b9eb1b4307f7c32dcb8a170f7c6c571f46ca
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56617562"
---
# <a name="gpu-activity-graph"></a>GPU アクティビティ グラフ
コンカレンシー ビジュアライザーの GPU アクティビティ グラフには、一定期間使用した DirectX エンジン数によってシステム上の DirectX アクティビティのレベルが測定され、表示されます。  グラフには、具体的にどのエンジンが使用されたかは表示されません。  GPU の作業を処理しているエンジンは使用中と見なされます。

## <a name="gpu-activity-graph-colors"></a>GPU アクティビティ グラフの色
 緑は現在のプロセスによる DirectX エンジンの消費量を示しています。

 淡い灰色は、システム上の他のプロセスによる DirectX エンジンの消費量を示しています。 他のプロセスによる DirectX エンジンの消費量を減らすには、システム上で実行される他のプロセスの数を削減します。

 白はシステム上で利用可能な未使用の DirectX エンジンを示します。 さらに用途が見つかればプロセスで使用できるエンジンです。 一部のエンジンは、特定のタスクにしか使用できません。

## <a name="see-also"></a>関連項目
- [使用状況ビュー](../profiling/utilization-view.md)