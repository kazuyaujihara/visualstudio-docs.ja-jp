---
title: メモリ使用量の分析
ms.custom: seodec18
ms.date: 01/02/2018
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 124b792e134b31a5964c8f202c7870a58bc0878b
ms.sourcegitcommit: 53bc4c11b82882ab658e34c65ae374060f823531
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71128248"
---
# <a name="analyze-memory-usage"></a>メモリ使用量の分析
デバッガーに統合された**メモリ使用量**診断ツールを使って、メモリ リークおよび非効率的なメモリ使用を見つけます。 メモリ使用量ツールを使用すると、マネージド メモリ ヒープ、およびネイティブ メモリ ヒープの 1 つまたは複数の *スナップショット* を取得できます。 .NET アプリ、ASP.NET アプリ、ネイティブ アプリ、または混在モード (.NET とネイティブ) アプリのスナップショットを収集できます。

- 単一のスナップショットを分析することにより、オブジェクト型のメモリ使用に対する相対的な影響を理解し、アプリ内でメモリが効率的に使用されていないコードを検出することができます。

- アプリの 2 つのスナップショットを比較 (diff) することにより、コード内で時間の経過に伴ってメモリ使用量が増加している箇所を検出することもできます。

方法については、「[メモリ使用量の分析](../profiling/memory-usage.md)」チュートリアルをご覧ください。  現時点では、.NET Core アプリのメモリ使用量を測定するには、デバッガーがアタッチされたツールを使用する必要があります。 その他のマネージド アプリとネイティブ アプリには、デバッガーがアタッチされたツールまたはされていないツールのいずれかを使用することができます。

Windows 7 以降ではデバッガーなしでプロファイル ツールを使用することができます。 Windows 8 以降では、デバッガーを使用してプロファイル ツールを実行する必要があります ( **[診断ツール]** ウィンドウ)。

## <a name="blogs-and-videos"></a>ブログとビデオ

[デバッグ中に CPU とメモリを分析する](https://devblogs.microsoft.com/visualstudio/analyze-cpu-memory-while-debugging/)

[Visual C++ ブログ:Visual C++ 2015 のメモリ プロファイル](https://devblogs.microsoft.com/cppblog/memory-profiling-in-visual-c-2015/)

## <a name="see-also"></a>関連項目

- [Visual Studio のプロファイル](../profiling/index.yml)
- [プロファイル ツールの概要](../profiling/profiling-feature-tour.md)