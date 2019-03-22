---
title: IJsDebugStackWalker インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 3fe30394-49c8-48e9-bde9-ffe5d79b2121
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d06af2c509339d9499f66e1f267c54c69951e225
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58150895"
---
# <a name="ijsdebugstackwalker-interface"></a>IJsDebugStackWalker インターフェイス
指定したスレッドのスタック ウォーカーを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp
IJsDebugStackWalker : public IUnknown;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IJsDebugStackWalker::GetNext メソッド](../../winscript/reference/ijsdebugstackwalker-getnext-method.md)|次のフレームを取得します。|  
  
## <a name="remarks"></a>Remarks  
 スタック ウォーカーはターゲット プロセスの停止中にのみ作成でき、そのプロセスが再び続行されると無効になります。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** jscript9diag.h です  
  
## <a name="see-also"></a>関連項目  
 [Windows スクリプト インターフェイスのリファレンス](../../winscript/reference/windows-script-interfaces-reference.md)