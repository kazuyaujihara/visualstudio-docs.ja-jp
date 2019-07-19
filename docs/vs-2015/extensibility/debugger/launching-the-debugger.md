---
title: デバッガーの起動 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], launching the debugger
- debugger [Debugging SDK], launching
ms.assetid: f24da1a1-f923-48b4-989f-18a22b581d1b
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e9c57079246dd52bd7fb44371999d0c3747dad40
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68149125"
---
# <a name="launching-the-debugger"></a>デバッガーの起動
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

デバッガーを起動するには、メソッドおよびイベントの適切な属性の適切なシーケンスを送信する必要があります。  
  
## <a name="sequences-of-methods-and-events"></a>メソッドとイベントのシーケンス  
  
1. セッション デバッグ マネージャー (SDM) が選択することによって呼び出される、**デバッグ**メニューをクリックして**開始**します。 参照してください[プログラムの起動](../../extensibility/debugger/launching-a-program.md)詳細についてはします。  
  
2. SDM コール[OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)メソッド。  
  
3. デバッグ エンジン (DE) のプロセス モデルに基づく、`IDebugProgramNodeAttach2::OnAttach`メソッドは、次の動作を決定するメソッドを次のいずれかを返します。  
  
     場合`S_FALSE`返されるか、デバッグ エンジン (DE) は、仮想マシンを処理中に読み込まれます。  
  
     \- または -  
  
     場合`S_OK`DE が読み込まれますが、返される、SDM のプロセスにします。 SDM には、次のタスクを実行します。  
  
    1. 呼び出し[GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) DE のエンジンの情報を取得します。  
  
    2. 併置デを作成します。  
  
    3. 呼び出し[アタッチ](../../extensibility/debugger/reference/idebugengine2-attach.md)します。  
  
4. DE 送信、 [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md)に SDM を`EVENT_SYNC`属性。  
  
5. DE 送信、 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md)に SDM を`EVENT_SYNC`属性。  
  
6. DE 送信、 [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md)に SDM を`EVENT_SYNC`属性。  
  
7. DE 送信、 [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md)に SDM を`EVENT_SYNC`属性。  
  
8. DE 送信、 [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md)に SDM を`EVENT_SYNC`属性。  
  
## <a name="see-also"></a>関連項目  
 [呼び出し元のデバッガー イベント](../../extensibility/debugger/calling-debugger-events.md)   
 [プログラムの起動](../../extensibility/debugger/launching-a-program.md)
