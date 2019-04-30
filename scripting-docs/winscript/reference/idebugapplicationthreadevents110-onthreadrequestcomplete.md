---
title: IDebugApplicationThreadEvents110::OnThreadRequestComplete |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThreadEvents110::OnThreadRequestComplete
ms.assetid: 7cdd73f3-d78e-4e2f-a204-7a1c45366b87
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5542d524506410e0a69dcb5addb6a7fe59209073
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440457"
---
# <a name="idebugapplicationthreadevents110onthreadrequestcomplete"></a>IDebugApplicationThreadEvents110::OnThreadRequestComplete
呼び出しに PDM のスレッドを使用して、スレッドの切り替えが完了します。  
  
> [!IMPORTANT]
> [IDebugApplicationThreadEvents110 インターフェイス](../../winscript/reference/idebugapplicationthreadevents110-interface.md)PDM v11.0 以降によって実装された以降には。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT OnThreadRequestComplete( void );  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドにパラメーターがありません。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationThreadEvents110 インターフェイス](../../winscript/reference/idebugapplicationthreadevents110-interface.md)