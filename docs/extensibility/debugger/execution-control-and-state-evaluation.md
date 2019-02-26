---
title: 実行制御と状態の評価 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], execution control
- expression evaluation, control of execution
ms.assetid: 55adde38-1622-4b51-83cb-ce1b04c1ca7a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bd04cfa1e271f94f1b37aa0fbd62e9b846d9a70d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56714687"
---
# <a name="execution-control-and-state-evaluation"></a>実行の制御と状態の評価
アプリケーションをデバッグするには、関数にステップ イン、ブレークポイント、停止、および実行を継続としてこのような実行管理機能を実装する必要があります。 Visual Studio ベースのデバッグ イベントの場合は、その実行コントロールは、デバッガーのコンポーネント間で送信されます。

## <a name="in-this-section"></a>このセクションの内容
 [コントロールのプログラム](../../extensibility/debugger/program-control.md)プログラム レベルで発生する次のルーチンを一覧表示: 次のステートメントを設定、実行、ステップ実行、続行、中断、および再開します。

 [ブレークポイントに関連するメソッド](../../extensibility/debugger/breakpoint-related-methods.md)バインドを定義および保留中の Visual Studio をサポートするためのブレークポイントの型。

 [スタック評価を呼び出す](../../extensibility/debugger/call-stack-evaluation.md)中断モード中に、コール スタックのスタック フレームを表示できるようにするメソッドの実装について説明します。

 [式の評価](../../extensibility/debugger/expression-evaluation-visual-studio-debugging-sdk.md)解析および IDE のウィンドウの 1 つに入力された式の評価にデバッグ エンジン (DE)、式の評価 (EE) およびセッション デバッグ マネージャーが関係する方法について説明します。

 [コントロールのイベント](../../extensibility/debugger/control-events.md)コントロール プログラムの実行中にイベントを送信するために使用するインターフェイスについて説明します。