---
title: 'IDebugApplicationThread110:: IsThreadCallable 可能 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThread110::IsThreadCallable
ms.assetid: 2a75a366-801d-47e0-bba3-51aa669e03a7
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5ff81190247454a4471a4150843d3fb0aaed5999
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574468"
---
# <a name="idebugapplicationthread110isthreadcallable"></a>IDebugApplicationThread110::IsThreadCallable
このスレッドが、SynchronousCallInThread など、PDM のスレッド切り替え機構を使用して行われた呼び出しを処理する状態であるかどうかを判断します。  
  
> [!IMPORTANT]
> [IDebugApplicationThread110 インターフェイス](../../winscript/reference/idebugapplicationthread110-interface.md)は、PDM version 11.0 以降で実装されています。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT IsThreadCallable([out, annotation("_Out_")] BOOL * pfIsCallable);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pfIsCallable`  
 [out] スレッドが呼び出し可能な場合は `true`。それ以外の場合は `false`。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationThread110 インターフェイス](../../winscript/reference/idebugapplicationthread110-interface.md)