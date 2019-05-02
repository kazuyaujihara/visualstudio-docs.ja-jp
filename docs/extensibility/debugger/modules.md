---
title: モジュール |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- modules
- debugging [Debugging SDK], modules
ms.assetid: c4cf2809-dbdb-4e75-9273-b3d3d77b67d0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 611d067030cd935f6957a976c8a3aa2b7d4f8ae3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925402"
---
# <a name="modules"></a>モジュール
デバッガーのアーキテクチャの観点から、*モジュール*:

- 実行可能ファイルや DLL などのコードの物理的なコンテナーです。

- そのシンボルを再読み込みし、それ自体を記述できます。 モジュールの説明は、IDE の [モジュール] ウィンドウに表示されます。

- によって表される、 [IDebugModule2](../../extensibility/debugger/reference/idebugmodule2.md)モジュールを記述するデバッグ エンジンによって作成されるインターフェイス。

## <a name="see-also"></a>関連項目
- [デバッガーの概念](../../extensibility/debugger/debugger-concepts.md)
- [IDebugModule2](../../extensibility/debugger/reference/idebugmodule2.md)