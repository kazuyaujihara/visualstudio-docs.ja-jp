---
title: デバッガーのコンポーネント |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], components
- components [Visual Studio SDK], debugging
- debugging [Debugging SDK], components
ms.assetid: 8b8ab77f-a134-495c-be42-3bc51aa62dfb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 28afdd7f12e7d83b042f5c705c85fa567fdbb979
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345892"
---
# <a name="debugger-components"></a>デバッガーのコンポーネント
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]デバッガーは、VSPackage として実装され、全体のデバッグ セッションを管理します。 デバッグ セッションには、次の要素が構成されています。

- **パッケージをデバッグするには。** [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]デバッガーがデバッグ中に関係なく同じユーザー インターフェイスを提供します。

- **セッション デバッグ マネージャー (SDM):** 一貫性のあるプログラム インターフェイスを提供します、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]さまざまなデバッグ エンジンの管理用のデバッガーです。 によって実装されている[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]します。

- **プロセス デバッグ マネージャー (PDM):** 実行中のすべてのインスタンスの管理、 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]、またはデバッグ中のすべてのプログラムの一覧。 によって実装されている[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]します。

- **デバッグ エンジン (DE)。** デバッグ中のプログラムの監視を担当、SDM を PDM は、実行中のプログラムの状態を通信し、プログラムの実行用メモリの状態のリアルタイム分析を提供するには、式エバリュエーターとシンボル プロバイダーとの対話と変数。 によって実装されます[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)](の対応言語) と、独自のランタイムをサポートするサード パーティ ベンダー。

- **式エバリュエーター (EE):** 変数と、プログラムが特定の時点で停止したときに、ユーザーが指定した式を動的に評価するためのサポートを提供します。 によって実装されます[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)](の対応言語) とは自分の言語をサポートするサード パーティ ベンダー。

- **シンボル プロバイダー (SP):** 呼ばれますシンボル ハンドラーでは、マップ、プログラムのデバッグ シンボル、プログラムの実行中のインスタンス (ソース コード レベルのデバッグや式の評価) 意味のある情報を提供できるようにします。 によって実装されている[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)](共通言語ランタイム [CLR] のシンボルと [PDB] プログラム データベース シンボル ファイルの形式)、デバッグ情報を保存する独自の専用メソッドを持つサード パーティ ベンダー。

  次の図は、Visual Studio デバッガーのこれらの要素間の関係を示します。

  ![コンポーネント デバッグの概要](../../extensibility/debugger/media/dbugcompovrview.gif "DBugCompOvrview")

## <a name="in-this-section"></a>このセクションの内容
 [デバッグ パッケージ](../../extensibility/debugger/debug-package.md)、debug パッケージの実行について説明します、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]シェルし、すべての UI を処理します。

 [プロセス デバッグ マネージャー](../../extensibility/debugger/process-debug-manager.md) PDM は、デバッグ可能なプロセス マネージャーの機能の概要を説明します。

 [セッション デバッグ マネージャー](../../extensibility/debugger/session-debug-manager.md) IDE に、デバッグ セッションの統合ビューを提供すると、SDM を定義します。 SDM は、DE を管理します。

 [デバッグ エンジン](../../extensibility/debugger/debug-engine.md)DE を提供するデバッグ サービスについて説明します。

 [操作モード](../../extensibility/debugger/operational-modes.md)IDE の操作に使用できる 3 つのモードの概要を説明します。 デザイン モード、実行モードと中断モード。 移行方法についても説明します。

 [式エバリュエーター](../../extensibility/debugger/expression-evaluator.md)実行時に、EE の目的について説明します。

 [シンボル プロバイダー](../../extensibility/debugger/symbol-provider.md) 、実装、シンボル プロバイダーの評価方法、変数や式について説明します。

 [ビジュアライザーとカスタム ビューアー入力](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)型のビジュアライザーをについて説明し、カスタム ビューアーは、どのような役割の両方をサポートしている、式エバリュエーターを再生します。

## <a name="related-sections"></a>関連項目
 [デバッガーの概念](../../extensibility/debugger/debugger-concepts.md)デバッグ アーキテクチャの主要な概念について説明します。

 [デバッガー コンテキスト](../../extensibility/debugger/debugger-contexts.md)DE が同時にして動作し、コード、ドキュメント、および式の評価コンテキスト内で方法について説明します。 3 つのコンテキスト、場所、位置、またはそれに関連する評価ごとに説明します。

 [タスクのデバッグ](../../extensibility/debugger/debugging-tasks.md)さまざまなプログラムの起動や式の評価などのタスクのデバッグへのリンクが含まれています。

## <a name="see-also"></a>関連項目
- [開始するには](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)