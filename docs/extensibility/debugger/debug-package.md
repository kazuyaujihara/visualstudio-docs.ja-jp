---
title: パッケージのデバッグ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], packages
ms.assetid: 99947fd4-fb87-4c69-b26c-65634e17d285
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fb1af813fabb1245d85fe18629d77a45f6acca3f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345906"
---
# <a name="debug-package"></a>パッケージをデバッグします。
デバッグ パッケージは、Visual Studio シェルで実行し、すべての UI を処理します。 Visual Studio のデバッグのインターフェイスを使用し、セッション デバッグ マネージャー (SDM) と通信します。

 中断イベントが、SDM を経由して送信は、中断モード、中断が発生したプログラムにフォーカスを変更して、実行モードからデバッガーを切り替えます。 デバッグ パッケージは、イベントによって送信される情報のスタック フレームとスレッドを追跡します。

 パッケージのデバッグには、言語またはランタイム環境の依存関係がありません。 実装またはデバッグ パッケージを変更する必要はありません。

 デバッグ パッケージがによって実装される*vsdebug.dll*します。

## <a name="see-also"></a>関連項目
- [セッション デバッグ マネージャー](../../extensibility/debugger/session-debug-manager.md)
- [スタック フレーム](../../extensibility/debugger/stack-frames.md)
- [スレッド](../../extensibility/debugger/threads.md)
- [デバッガーのコンポーネント](../../extensibility/debugger/debugger-components.md)