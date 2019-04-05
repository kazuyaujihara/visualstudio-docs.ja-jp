---
title: 添付ファイルの起動に基づく |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f4a967b48f7c904ecc22d0b3ea077ae5cecd2625
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56718964"
---
# <a name="launch-based-attachment"></a>起動ベースの添付ファイル
プログラムを起動ベースの添付ファイルは自動です。 によって、SDM をプログラムをホストするプロセスを起動すると起動ベースの添付ファイルは手動の添付ファイルのメソッドのようなパスに従います。 詳しくは、[プログラムにアタッチ](../../extensibility/debugger/attaching-to-the-program.md)を参照してください。

## <a name="the-attaching-process"></a>プロセスを接続します。
 主な違いは、次のイベントのシーケンス、**アタッチ**呼び出すと、次のようにします。

1.  送信、 **IDebugEngineCreateEvent2** SDM にイベント オブジェクト。 詳細については、[イベントを送信する](../../extensibility/debugger/sending-events.md)を参照してください。

2.  呼び出す、`IDebugProgram2::GetProgramId`メソッドを**IDebugProgram2**に渡されたインターフェイス、**アタッチ**メソッド。

3.  送信、 **IDebugProgramCreateEvent2** 、SDM を通知するイベント オブジェクトをローカル**IDebugProgram2** DE にプログラムを表現するオブジェクトが作成されました。

4.  送信、 [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) SDM を起動したプロセスに、新しいスレッドを作成することを通知するイベント オブジェクト。

## <a name="see-also"></a>関連項目
- [必要なイベントを送信します。](../../extensibility/debugger/sending-the-required-events.md)
- [デバッグするプログラムを有効にします。](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)