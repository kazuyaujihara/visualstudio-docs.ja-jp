---
title: IEnumJsStackFrames Interface |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 49e7b425-df17-4d7f-87ff-0bc82715c911
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b4a635a802ae84b8e839159f5e2f1c4c461e05ae
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572032"
---
# <a name="ienumjsstackframes-interface"></a>IEnumJsStackFrames インターフェイス
JavaScript の jscript9diag.dll でスタック アンワインドが可能になるようにデバッガーによって実装されます。  
  
## <a name="syntax"></a>構文  
  
```cpp
IEnumJsStackFrames : public IUnknown;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名|説明|  
|----------|-----------------|  
|[IEnumJsStackFrames::Next メソッド](../../winscript/reference/ienumjsstackframes-next-method.md)|指定した数のフレームを取得します。|  
|[IEnumJsStackFrames::Reset メソッド](../../winscript/reference/ienumjsstackframes-reset-method.md)|スタック フレームを最初の要素の前の位置にリセットします。|  
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [Windows スクリプト インターフェイスのリファレンス](../../winscript/reference/windows-script-interfaces-reference.md)