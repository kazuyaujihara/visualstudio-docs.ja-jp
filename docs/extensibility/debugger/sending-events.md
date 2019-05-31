---
title: イベントの送信 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], sending events
ms.assetid: 064231e7-59b5-4437-8240-a23c0a7ec2a9
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2a2c87b2e05e4ffe94d77333095438f43b644976
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66311339"
---
# <a name="send-events"></a>イベントを送信します。
デバッガーとデバッグ エンジン (DE) 間の通信メカニズムは、DCOM に基づいてイベント モデル。 イベントは、COM オブジェクトとして送信され、各イベントを指定するパラメーターには。

- この DE イベントと呼ばれます。

- 変更点の説明。

- プロセス、プログラム、およびイベントの発生場所のコンテキストを識別するスレッドの情報。 プロセスは、ドイツから送信されたイベントは送信されません。

- イベントが同期または非同期であるかどうかを示すイベントの種類。

  メソッドを使用してすべてのデバッグ イベントが送信される[IDebugEventCallback2::Event](../../extensibility/debugger/reference/idebugeventcallback2-event.md)します。

## <a name="in-this-section"></a>このセクションの内容
 [イベント ソース](../../extensibility/debugger/event-sources-visual-studio-sdk.md)イベントの 2 つのソースについて説明します。 デバッグ エンジン (DE) とセッション デバッグ マネージャー (SDM)。

 [イベントの種類がサポートされている](../../extensibility/debugger/supported-event-types.md)現在サポートされているイベントの種類について説明します。 非同期と同期します。

 [イベントの説明](../../extensibility/debugger/event-descriptions.md)イベントとその使用する理由を定義します。

## <a name="related-sections"></a>関連項目
 [カスタム デバッグ エンジンを作成する](../../extensibility/debugger/creating-a-custom-debug-engine.md)インタープリターまたはオペレーティング システムは、デバッグ サービスを提供すると、DE のしくみについて説明します。