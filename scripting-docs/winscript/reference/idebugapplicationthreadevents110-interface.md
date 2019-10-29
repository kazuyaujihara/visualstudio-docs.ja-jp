---
title: IDebugApplicationThreadEvents110 Interface |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThreadEvents110 Interface
ms.assetid: 91a98b0e-7c81-4118-af75-82f75fd4f25a
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5dd666d825c40155675714f5945209f22198993c
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72984401"
---
# <a name="idebugapplicationthreadevents110-interface"></a>IDebugApplicationThreadEvents110 インターフェイス
スレッドイベントをさらに追加します。 これらのイベントはローカルのみです。 つまり、PDM アプリケーションスレッドオブジェクト ( [IDebugApplicationThread インターフェイス](../../winscript/reference/idebugapplicationthread-interface.md)を実装するオブジェクト) の[IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) advise メソッドとアドバイズメソッドを使用して、デバッグ中のプロセスでのみサブスクライブできます。 これらは、送信元のスレッドで発生します。  
  
> [!IMPORTANT]
> このインターフェイスは、PDM v11.0 以降によって実装されます。 activdbg100.h にあります。  
  
## <a name="methods"></a>メソッド  
 `IDebugActivationThreadEvents110` インターフェイスは、以下のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugApplicationThreadEvents110 ::OnBeginThreadRequest](../../winscript/reference/idebugapplicationthreadevents110-onbeginthreadrequest.md)|PDM のスレッド切り替えを使用してスレッドへの呼び出しが開始されました。|  
|[IDebugApplicationThreadEvents110::OnResumeFromBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onresumefrombreakpoint.md)|スレッドはブレークポイントから再開され、再びアクティブになります。|  
|[IDebugApplicationThreadEvents110::OnSuspendForBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onsuspendforbreakpoint.md)|スレッドはブレークポイントを中断しているため、スレッドを完全に中断する必要のある呼び出しを処理できます。|  
|[IDebugApplicationThreadEvents110::OnThreadRequestComplete](../../winscript/reference/idebugapplicationthreadevents110-onthreadrequestcomplete.md)|PDM のスレッド切り替えを使用したスレッドの呼び出しが完了しました。|