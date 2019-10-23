---
title: 'IDebugApplication:: StepOutComplete |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.StepOutComplete
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::StepOutComplete
ms.assetid: 9675b214-7be5-4cf7-a63f-7865f3c54371
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f50d7e8a8936e52f4177450e7d163c4cfeaa55df
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571041"
---
# <a name="idebugapplicationstepoutcomplete"></a>IDebugApplication::StepOutComplete
シングルステップモードの言語エンジンが呼び出し元に戻ることをプロセスデバッグマネージャーに通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT StepOutComplete();  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドはパラメーターを受け取りません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 言語エンジンは、呼び出し元に戻る直前に、このメソッドをシングルステップモードで呼び出します。 プロセスデバッグマネージャーは、この機会を使用して、最初の機会に中断する必要がある他のすべてのスクリプトエンジンに通知します。 この手法では、言語間のステップモードが実装されます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplication インターフェイス](../../winscript/reference/idebugapplication-interface.md)