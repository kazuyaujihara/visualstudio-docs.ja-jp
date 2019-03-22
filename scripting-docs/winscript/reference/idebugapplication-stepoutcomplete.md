---
title: IDebugApplication::StepOutComplete |Microsoft Docs
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
ms.openlocfilehash: 04f8ecfb835199afa0a60f3fde3c8fbdc8812240
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58153137"
---
# <a name="idebugapplicationstepoutcomplete"></a>IDebugApplication::StepOutComplete
シングル ステップ モードで、言語エンジンがその呼び出し元に戻ることをプロセス デバッグ マネージャーに通知します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT StepOutComplete();  
```  
  
#### <a name="parameters"></a>パラメーター  
 このメソッドには、パラメーターはありません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 言語エンジンは、その呼び出し元に戻る直前に、シングル ステップ モードでこのメソッドを呼び出します。 プロセス デバッグ マネージャーでは、この機会を使用して、最初のチャンスに中断する必要があります、その他のすべてのスクリプト エンジンに通知します。 この手法は、モードの実装方法、言語間のステップです。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplication インターフェイス](../../winscript/reference/idebugapplication-interface.md)