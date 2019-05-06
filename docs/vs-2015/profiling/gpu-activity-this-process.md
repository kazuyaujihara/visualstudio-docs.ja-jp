---
title: GPU アクティビティ (このプロセス) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.gpuexecution
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 0956edbf-9bcd-4afe-9287-fda628648ca0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b616e307b3c42b09662be3fdad290ea9f740637c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62434151"
---
# <a name="gpu-activity-this-process"></a>GPU アクティビティ (このプロセス)
コンカレンシー ビジュアライザーのスレッド ビューの **[GPU アクティビティ (このプロセス)]** セグメントは、GPU が現在のプロセスに代わり、要求を処理していた時間を示します。 これらの要求はダイレクト メモリ アクセス (DMA) パケットとして GPU に送信されます。 セグメントの長さは、GPU が現在のプロセスに代わって DMA パケットを処理していた時間を表します。

 GPU アクティビティ セグメントを選択した場合、**[現在]** タブには処理された DMA パケットの情報が表示されます。 情報には、パケットが DirectX に関連するハードウェア キューで待機していた時間、パケットを送信したプロセス、およびパケットの処理に要した時間が含まれます。 現在のプロセス以外のプロセスによって、DMA パケットが GPU に物理的に送信されることがあります。 現在のプロセスに代わって他のプロセスが GPU に作業を送信すると、コンカレンシー ビジュアライザーによって検出されます。