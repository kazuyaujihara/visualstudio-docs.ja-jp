---
title: プロセス |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], processes
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 82718a7ceb7a18f9978840f35ca0c5fce5628e81
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977972"
---
# <a name="processes"></a>プロセス
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

デバッガーのアーキテクチャの観点から、**プロセス**:  
  
- プログラムの一連のコンテナーです。 Windows プロセス、スレッドのセットのコンテナーであると密接に似ています。  
  
- 名前、識別子、または物理的な識別子で自身を識別できます。  
  
- 実行中のすべてのプログラム (とそのスレッド) を列挙できます。  
  
- 自体では、実行されているポートとそれを含んでいるマシンを記述できます。  
  
- 1 つを作成したり、他のプログラムの作成、プログラムを終了またはプログラムを停止します。  
  
- によって表される、 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)インターフェイスで、プロセスを起動するときに作成されます。 いずれかのセッション デバッグ マネージャー (SDM) プロセスの起動時または[LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)します。  
  
  パッケージのデバッグは呼び出すことによって、プロセスにデバッグ エンジン (DE) をアタッチすることができます[アタッチ](../../extensibility/debugger/reference/idebugprocess2-attach.md)します。 つまり、DE が処理できるプロセスで実行されているすべての可能なプログラムにアタッチします。 たとえば場合、DE、共通言語ランタイムは、プロセスにアタッチして、マネージ コードが実行されているプログラムのみにアタッチします。  
  
## <a name="see-also"></a>関連項目  
 [プログラム](../../extensibility/debugger/programs.md)   
 [スレッド](../../extensibility/debugger/threads.md)   
 [デバッガーの概念](../../extensibility/debugger/debugger-concepts.md)   
 [パッケージをデバッグします。](../../extensibility/debugger/debug-package.md)   
 [デバッグ エンジン](../../extensibility/debugger/debug-engine.md)   
 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [添付](../../extensibility/debugger/reference/idebugprocess2-attach.md)
