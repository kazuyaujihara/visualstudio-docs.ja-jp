---
title: IDebugApplicationThread110::GetActiveThreadRequestCount |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThread110::GetActiveThreadRequestCount
ms.assetid: 025d2072-1d7f-4448-8aa3-38a014313570
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3df2f0c44e42cf9e2c2aa846db4b88821fd73996
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440568"
---
# <a name="idebugapplicationthread110getactivethreadrequestcount"></a>IDebugApplicationThread110::GetActiveThreadRequestCount
現在処理されているメカニズムを切り替え、PDM のスレッドからのスレッドの要求の数を返します。 この番号は 0 または 1 では、通常は。 ただし、数場合があります高い 1 つのスレッドの呼び出しの処理を開始がスレッドからの同期呼び出しをトリガーまたはそれ以外の場合、スレッドを中断でき、着信呼び出しを再度処理する (トリガーすることなどによって、 [IRemoteDebugApplicationEvents インターフェイス](../../winscript/reference/iremotedebugapplicationevents-interface.md)デバッガー スレッドで発行されるイベント)。  
  
> [!IMPORTANT]
> [IDebugApplicationThread110 インターフェイス](../../winscript/reference/idebugapplicationthread110-interface.md)PDM v11.0 以降によって実装された以降には。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetActiveThreadRequestCount([out, annotation("_Out_")] UINT * puiThreadRequests);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `puiThreadRequests`  
 [out]スレッドの要求の数。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationThread110 インターフェイス](../../winscript/reference/idebugapplicationthread110-interface.md)