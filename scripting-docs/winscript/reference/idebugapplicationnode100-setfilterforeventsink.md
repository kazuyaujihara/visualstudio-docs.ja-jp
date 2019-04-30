---
title: IDebugApplicationNode100::SetFilterForEventSink |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNode100::SetFilterForEventSink
ms.assetid: cfb34efe-c6e1-4692-8ffd-3ede3a24cd4b
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 662c433134bc278f343381edcb4aedf383af6078
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446681"
---
# <a name="idebugapplicationnode100setfilterforeventsink"></a>IDebugApplicationNode100::SetFilterForEventSink
特定のフィルターを設定[IDebugApplicationNodeEvents インターフェイス](../../winscript/reference/idebugapplicationnodeevents-interface.md)実装します。 PDM はこれらが作成または削除するときにイベントを送信できなくなるように、アプリケーションのコンパイラ生成の子ノードをフィルターするスクリプト デバッガーができます。 既定では、すべてのノードが送信されます。  
  
> [!IMPORTANT]
> [IDebugApplicationNode100 インターフェイス](../../winscript/reference/idebugapplicationnode100-interface.md)PDM v10.0 によって実装およびそれ以降は、します。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT SetFilterForEventSink(        [in] DWORD dwCookie,        [in] APPLICATION_NODE_EVENT_FILTER filter        );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwCookie`  
 フィルターのクッキー。  
  
 `filter`  
 フィルターです。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationNode100 インターフェイス](../../winscript/reference/idebugapplicationnode100-interface.md)