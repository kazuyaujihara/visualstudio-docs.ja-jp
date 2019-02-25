---
title: デバッガーの概念 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK]
ms.assetid: 2d371d38-f1a0-4a9a-8ea3-100e8c0149b7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7e3a9043215c5242246e54dc3e1eb2e85cd26c91
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56711190"
---
# <a name="debugger-concepts"></a>デバッガーの概念
Visual Studio のデバッグ パッケージをビルドするには、パッケージの設計で使用されるアーキテクチャの概念を理解する必要があります。

## <a name="in-this-section"></a>このセクションの内容
 [デバッグ セッションは](../../extensibility/debugger/debug-session.md)デバッグのアーキテクチャでは、セッションの役割について説明します。

 [サーバー](../../extensibility/debugger/servers-visual-studio-sdk.md)抽象と物理の両方の用語で、アーキテクチャのデバッグの観点からどのようなサーバーを定義します。

 [ポート サプライヤー](../../extensibility/debugger/port-suppliers.md)デバッグのアーキテクチャの観点からどのようなポート サプライヤーを定義します。

 [ポート](../../extensibility/debugger/ports.md)どのようなポートとは、デバッグのアーキテクチャの観点から定義します。

 [プロセス](../../extensibility/debugger/processes.md)デバッグのアーキテクチャの観点からどのようなプロセスを定義します。

 [プログラム ノード](../../extensibility/debugger/program-nodes.md)デバッグ自体とで実行されているプロセスを特定できる方法を含めて、アーキテクチャの観点からプログラム ノードを定義します。

 [プログラム](../../extensibility/debugger/programs.md)デバッグのアーキテクチャの観点からのプログラムを定義します。

 [スレッド](../../extensibility/debugger/threads.md)デバッグのアーキテクチャの観点からのスレッドの特性を定義します。

 [スタック フレーム](../../extensibility/debugger/stack-frames.md)デバッグのアーキテクチャの観点からのスタック フレームを定義します。 スタック フレームは、スレッドの実行コンテキストを提供するスタックの抽象化です。

 [モジュール](../../extensibility/debugger/modules.md)のアーキテクチャをデバッグ実行可能ファイルや DLL などのコードの物理コンテナーとしての観点から、モジュールを定義します。

 [ブレークポイント](../../extensibility/debugger/breakpoints-visual-studio-sdk.md)3 種類のブレークポイントを定義します。-保留中、バインド、およびエラー-デバッグのアーキテクチャの観点から。

## <a name="related-sections"></a>関連項目
 [デバッガー コンテキスト](../../extensibility/debugger/debugger-contexts.md)デバッグ エンジン (DE) が同時にして動作し、コード、ドキュメント、および式の評価コンテキスト内で方法について説明します。 3 つのコンテキスト、場所、位置、またはそれに関連する評価ごとに説明します。

 [デバッガーのコンポーネント](../../extensibility/debugger/debugger-components.md)デバッグ エンジン (DE)、式エバリュエーター (EE) シンボル ハンドラー (SH) など、Visual Studio デバッグ コンポーネントの概要を説明します。

 [タスクのデバッグ](../../extensibility/debugger/debugging-tasks.md)さまざまなプログラムの起動や式の評価などのタスクのデバッグへのリンクが含まれています。