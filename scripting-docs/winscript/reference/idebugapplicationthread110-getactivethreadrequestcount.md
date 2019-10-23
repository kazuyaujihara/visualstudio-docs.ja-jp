---
title: 'IDebugApplicationThread110:: GetActiveThreadRequestCount |Microsoft Docs'
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
ms.openlocfilehash: e7f038c1d0958701a14899825a2adb0a11cf604d
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574489"
---
# <a name="idebugapplicationthread110getactivethreadrequestcount"></a>IDebugApplicationThread110::GetActiveThreadRequestCount
現在処理されている PDM のスレッド切り替え機構からのスレッド要求の数を返します。 通常、この数値は0または1です。 ただし、1つのスレッド呼び出しで処理が開始されてもスレッドからの同期呼び出しがトリガーされ、それ以外の場合はスレッドが中断され、着信呼び出しを再び処理できるようになります (たとえば、Iremotedebugapplicationevents をトリガーするなど)。 [インターフェイス](../../winscript/reference/iremotedebugapplicationevents-interface.md)イベント。デバッガースレッドで発行されます)。  
  
> [!IMPORTANT]
> [IDebugApplicationThread110 インターフェイス](../../winscript/reference/idebugapplicationthread110-interface.md)は、PDM version 11.0 以降で実装されています。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetActiveThreadRequestCount([out, annotation("_Out_")] UINT * puiThreadRequests);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `puiThreadRequests`  
 入出力スレッド要求の数。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationThread110 インターフェイス](../../winscript/reference/idebugapplicationthread110-interface.md)