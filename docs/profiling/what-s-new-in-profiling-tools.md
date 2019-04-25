---
title: Visual Studio 2017 でのプロファイリングの新機能 | Microsoft Docs
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling
- what's new
ms.assetid: d4736cc8-8961-4089-be9e-d5190ce8353c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
monikerRange: vs-2017
ms.openlocfilehash: 8fcd01198877ef06eb398ce99fe467deb923546c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62999224"
---
# <a name="whats-new-in-profiling-tools-in-includevsdev15miscincludesvsdev15mdmd"></a>[!include[vs_dev15](../misc/includes/vs_dev15_md.md)] プロファイリング ツールの新機能

診断ツールに、修正が必要なアプリの問題を識別できる新しい視覚化が追加されました。 診断ツールに ASP.NET アプリのサポートが追加されました。

詳しくは、「[[!include[vs_dev15](../misc/includes/vs_dev15_md.md)] リリース ノート](/visualstudio/releasenotes/vs2017-relnotes)」をご覧ください。

パフォーマンス分析の主な領域に重点を置くことができる、**概要**タブがツールに追加されました。 概要タブには発生したイベントの数が表示され、ヒープのスナップショットを作成して、CPU 使用率のデータ収集を直ちに有効にすることができます。 このビューには、[Application Insights](/azure/azure-monitor/app/visual-studio) または [UI Analysis](/visualstudio/releasenotes/vs2017-relnotes) のイベントが表示されます。 また、Visual Studio Enterprise では、ビューに IntelliTrace イベントも表示されます。

![診断ツールの概要タブ](../profiling/media/diag-tools-summary-tab-2.png "DiagToolsSummaryTab")

CPU 使用率ツールに[新しい視覚化](../profiling/Beginners-Guide-to-Performance-Profiling.md)が加えられ、パフォーマンスの問題の原因になっている可能性が最も高い関数を識別できます。 新しい**呼び出し元/呼び出し先**ビューによって、選択した関数に対して、または選択した関数から行われる関数呼び出しのコストを調べることができます。

![診断ツールの [呼び出し元/呼び出し先] ビュー](../profiling/media/diag-tools-caller-callee-2.png "DiagToolsCallerCallee")

## <a name="see-also"></a>関連項目

- [Visual Studio のプロファイル](../profiling/index.md)
- [プロファイル ツールの概要](../profiling/profiling-feature-tour.md)