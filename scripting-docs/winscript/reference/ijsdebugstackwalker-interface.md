---
title: IJsDebugStackWalker Interface |Microsoft Docs
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
ms.openlocfilehash: 3b06b8c1f9282c42599c798030440c30450ef6dd
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574016"
---
# <a name="ijsdebugstackwalker-interface"></a>IJsDebugStackWalker インターフェイス
指定したスレッドのスタック ウォーカーを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp
IJsDebugStackWalker : public IUnknown;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名|説明|  
|----------|-----------------|  
|[IJsDebugStackWalker::GetNext メソッド](../../winscript/reference/ijsdebugstackwalker-getnext-method.md)|次のフレームを取得します。|  
  
## <a name="remarks"></a>Remarks  
 スタック ウォーカーはターゲット プロセスの停止中にのみ作成でき、そのプロセスが再び続行されると無効になります。  
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [Windows スクリプト インターフェイスのリファレンス](../../winscript/reference/windows-script-interfaces-reference.md)