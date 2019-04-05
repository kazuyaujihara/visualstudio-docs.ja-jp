---
title: デバッガーのコンポーネント |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], components
- components [Visual Studio SDK], debugging
- debugging [Debugging SDK], components
ms.assetid: 8b8ab77f-a134-495c-be42-3bc51aa62dfb
caps.latest.revision: 31
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 12f865e7d4c44cfa4002b330ed85ec95f95a8ef9
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977653"
---
# <a name="debugger-components"></a>デバッガーのコンポーネント
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]デバッガーは、VSPackage として実装され、全体のデバッグ セッションを管理します。 デバッグ セッションには、次の要素が構成されています。  
  
- **パッケージをデバッグするには。**[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]デバッガーがデバッグ中に関係なく同じユーザー インターフェイスを提供します。  
  
- **セッション デバッグ マネージャー (SDM):** 一貫性のあるプログラム インターフェイスを提供します、[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]さまざまなデバッグ エンジンの管理用のデバッガーです。 によって実装されている[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]します。  
  
- **プロセス デバッグ マネージャー (PDM):** 実行中のすべてのインスタンスの管理、 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]、またはデバッグ中のすべてのプログラムの一覧。 によって実装されている[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]します。  
  
- **デバッグ エンジン (DE)。** デバッグ中のプログラムの監視を担当、SDM を PDM は、実行中のプログラムの状態を通信し、プログラムの実行用メモリの状態のリアルタイム分析を提供するには、式エバリュエーターとシンボル プロバイダーとの対話と変数。 によって実装されます[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)](の対応言語) と、独自のランタイムをサポートするサード パーティ ベンダー。  
  
- **式エバリュエーター (EE):** 変数と、プログラムが特定の時点で停止したときに、ユーザーが指定した式を動的に評価するためのサポートを提供します。 によって実装されます[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)](の対応言語) とは自分の言語をサポートするサード パーティ ベンダー。  
  
- **シンボル プロバイダー (SP):** 呼ばれますシンボル ハンドラーでは、マップ、プログラムのデバッグ シンボル、プログラムの実行中のインスタンス (ソース コード レベルのデバッグや式の評価) 意味のある情報を提供できるようにします。 によって実装されている[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)](共通言語ランタイム [CLR] のシンボルと [PDB] プログラム データベース シンボル ファイルの形式)、デバッグ情報を保存する独自の専用メソッドを持つサード パーティ ベンダー。  
  
  次の図は、Visual Studio デバッガーのこれらの要素間の関係を示します。  
  
  ![コンポーネント デバッグの概要](../../extensibility/debugger/media/dbugcompovrview.gif "DBugCompOvrview")  
  
## <a name="in-this-section"></a>このセクションの内容  
 [パッケージのデバッグ](../../extensibility/debugger/debug-package.md)  
 実行されるデバッグ パッケージについて説明します、[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]シェルし、すべての UI を処理します。  
  
 [プロセス デバッグ マネージャー](../../extensibility/debugger/process-debug-manager.md)  
 デバッグ可能なプロセス マネージャーであると、PDM の機能の概要を示します。  
  
 [セッション デバッグ マネージャー](../../extensibility/debugger/session-debug-manager.md)  
 IDE、デバッグ セッションの統合ビューを提供すると、SDM を定義します。 SDM は、DE を管理します。  
  
 [デバッグ エンジン](../../extensibility/debugger/debug-engine.md)  
 デバッグ、DE を提供するサービスについて説明します。  
  
 [操作モード](../../extensibility/debugger/operational-modes.md)  
 IDE の操作に使用できる 3 つのモードの概要を説明します。 デザイン モード、実行モードと中断モード。 移行方法についても説明します。  
  
 [式エバリュエーター](../../extensibility/debugger/expression-evaluator.md)  
 実行時に、EE の目的について説明します。  
  
 [シンボル プロバイダー](../../extensibility/debugger/symbol-provider.md)  
 方法については、実装、シンボル プロバイダー評価変数よぶ式について説明します。  
  
 [型のビジュアライザーとカスタム ビューアー](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)  
 について説明します型のビジュアライザーおよびカスタム ビューアーし、どのような役割の両方をサポートしている、式エバリュエーターを再生します。  
  
## <a name="related-sections"></a>関連項目  
 [デバッガーの概念](../../extensibility/debugger/debugger-concepts.md)  
 デバッグ アーキテクチャの主要な概念をについて説明します。  
  
 [デバッガー コンテキスト](../../extensibility/debugger/debugger-contexts.md)  
 コード、ドキュメント、および式の評価のコンテキスト内で、DE がどの同時に動作について説明します。 3 つのコンテキスト、場所、位置、またはそれに関連する評価ごとに説明します。  
  
 [タスクのデバッグ](../../extensibility/debugger/debugging-tasks.md)  
 プログラムを起動して、式の評価などのさまざまなデバッグ タスクへのリンクが含まれています。  
  
## <a name="see-also"></a>関連項目  
 [作業の開始](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)
