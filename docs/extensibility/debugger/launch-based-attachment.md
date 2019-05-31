---
title: 添付ファイルの起動に基づく |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 638eaea19b4f21e749fbd3db845f18eb573420f2
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66344144"
---
# <a name="launch-based-attachment"></a>起動ベースの添付ファイル
プログラムを起動ベースの添付ファイルは自動です。 によって、SDM をプログラムをホストするプロセスを起動すると起動ベースの添付ファイルは手動の添付ファイルのメソッドのようなパスに従います。 詳しくは、次を参照してください。[プログラムにアタッチ](../../extensibility/debugger/attaching-to-the-program.md)します。

## <a name="the-attaching-process"></a>プロセスを接続します。
 主な違いは、次のイベントのシーケンス、**アタッチ**呼び出すと、次のようにします。

1. 送信、 **IDebugEngineCreateEvent2** SDM にイベント オブジェクト。 詳細については、次を参照してください。[イベントを送信する](../../extensibility/debugger/sending-events.md)します。

2. 呼び出す、`IDebugProgram2::GetProgramId`メソッドを**IDebugProgram2**に渡されたインターフェイス、**アタッチ**メソッド。

3. 送信、 **IDebugProgramCreateEvent2** 、SDM を通知するイベント オブジェクトをローカル**IDebugProgram2** DE にプログラムを表現するオブジェクトが作成されました。

4. 送信、 [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) SDM を起動したプロセスに、新しいスレッドを作成することを通知するイベント オブジェクト。

## <a name="see-also"></a>関連項目
- [必要なイベントを送信します。](../../extensibility/debugger/sending-the-required-events.md)
- [デバッグするプログラムを有効にします。](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)