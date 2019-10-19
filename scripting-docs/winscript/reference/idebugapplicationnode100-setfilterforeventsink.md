---
title: 'IDebugApplicationNode100:: SetFilterForEventSink |Microsoft Docs'
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
ms.openlocfilehash: 4f85241bee7b35d40bf193a613a6fefda4265be6
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574734"
---
# <a name="idebugapplicationnode100setfilterforeventsink"></a>IDebugApplicationNode100::SetFilterForEventSink
特定の[IDebugApplicationNodeEvents インターフェイス](../../winscript/reference/idebugapplicationnodeevents-interface.md)実装にフィルターを設定します。 これにより、スクリプトデバッガーは、コンパイラによって生成された子アプリケーションノードをフィルターで除外できます。これにより、これらの作成時または削除時に、PDM がイベントを送信しなくなります。 既定では、すべてのノードが送信されます。  
  
> [!IMPORTANT]
> [IDebugApplicationNode100 インターフェイス](../../winscript/reference/idebugapplicationnode100-interface.md)は、PDM version 10.0 以降で実装されています。 activdbg100.h にあります。  
  
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