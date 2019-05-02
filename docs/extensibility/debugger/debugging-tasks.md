---
title: タスクのデバッグ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], tasks
ms.assetid: 5d60e9e8-305e-4a48-829f-b9440fc8af7b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 299db84fb06679bfbf9dff92234c944cbdec6295
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925818"
---
# <a name="debug-tasks"></a>タスクをデバッグします。
起動できることをプログラムをデバッグして、デバッグ エンジン (DE) をアタッチする必要があります。 そう、DE は、以前に起動されたプログラムにアタッチする必要があります。 アタッチされると、デは特定のスタートアップ イベントを生成する必要があります。 応答では、パッケージのデバッグは、IDE で設定されたブレークポイントをバインドしようとします。 プログラムがバインドされたブレークポイントに達するときに停止し、ユーザー入力を待機します。

## <a name="in-this-section"></a>このセクションの内容
 [セキュリティの問題](../../extensibility/debugger/security-issues.md)プログラムをデバッグするために必要なセキュリティ手順について説明します。

 [プログラムを起動](../../extensibility/debugger/launching-a-program.md)DE では、プログラムを起動するオペレーティング システムの呼び出しを指定する方法の手順について説明します。

 [プログラムに直接アタッチ](../../extensibility/debugger/attaching-directly-to-a-program.md)が既に実行中のプロセスでプログラムをデバッグするために使用するプロセスについて説明します。

 [起動後、スタートアップ イベントを送信](../../extensibility/debugger/sending-startup-events-after-a-launch.md)まで、プログラムは、メイン エントリ ポイントで、デバッグの準備ができて、DE がプログラムにアタッチされると発生するイベントを一覧表示されます。

 [実行の制御](../../extensibility/debugger/control-of-execution.md)DE 通常送信する方法のエントリ ポイント イベント、読み込み完了イベントの場合、または、状況に応じて、停止イベントについて説明します。

 [ブレークポイントをバインド](../../extensibility/debugger/binding-breakpoints.md)方法については、ユーザーは、ブレークポイントを設定、IDE、要求の作成し、プロンプトをブレークポイントを作成する、デバッグ セッションをについて説明します。

 [式の評価](../../extensibility/debugger/evaluating-expressions.md)式の作成方法と、式が評価されるときの動作について説明します。

 [データを視覚化および](../../extensibility/debugger/visualizing-and-viewing-data.md)(EE) の式エバリュエーターで型のビジュアライザーおよびカスタム ビューアーをサポートする方法について説明します。

## <a name="related-sections"></a>関連項目
 [デバッガーの概念](../../extensibility/debugger/debugger-concepts.md)デバッグ アーキテクチャの主要な概念について説明します。

 [デバッガーのコンポーネント](../../extensibility/debugger/debugger-components.md)Visual Studio のデバッグ、DE、EE、およびシンボル ハンドラー (SH) のコンポーネントの概要を説明します。

 [デバッガー コンテキスト](../../extensibility/debugger/debugger-contexts.md)DE が同時にして動作し、コード、ドキュメント、および式の評価コンテキスト内で方法について説明します。 3 つのコンテキスト、場所、位置、またはそれに関連する評価ごとに説明します。

## <a name="see-also"></a>関連項目
 [開始するには](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)