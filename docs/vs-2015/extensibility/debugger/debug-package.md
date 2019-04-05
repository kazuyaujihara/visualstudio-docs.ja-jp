---
title: パッケージのデバッグ |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], packages
ms.assetid: 99947fd4-fb87-4c69-b26c-65634e17d285
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: dda8b1ac6eaa2cd5352d441600ae720c3aac321c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977040"
---
# <a name="debug-package"></a>パッケージのデバッグ
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

デバッグ パッケージは、Visual Studio シェルで実行し、すべての UI を処理します。 Visual Studio のデバッグのインターフェイスを使用し、セッション デバッグ マネージャー (SDM) と通信します。  
  
 中断イベントが、SDM を経由して送信は、中断モード、中断が発生したプログラムにフォーカスを変更して、実行モードからデバッガーを切り替えます。 デバッグ パッケージは、イベントによって送信される情報のスタック フレームとスレッドを追跡します。  
  
 パッケージのデバッグには、言語またはランタイム環境の依存関係がありません。 実装またはデバッグ パッケージを変更する必要はありません。  
  
 デバッグ パッケージは、vsdebug.dll によって実装されます。  
  
## <a name="see-also"></a>関連項目  
 [セッション デバッグ マネージャー](../../extensibility/debugger/session-debug-manager.md)   
 [スタック フレーム](../../extensibility/debugger/stack-frames.md)   
 [スレッド](../../extensibility/debugger/threads.md)   
 [デバッガーのコンポーネント](../../extensibility/debugger/debugger-components.md)
