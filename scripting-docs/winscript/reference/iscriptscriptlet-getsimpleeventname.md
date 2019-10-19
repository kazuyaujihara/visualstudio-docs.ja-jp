---
title: 'IScriptScriptlet レット:: GetSimpleEventName |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptScriptlet. GetSimpleEventName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptScriptlet::GetSimpleEventName
ms.assetid: 012eb555-b26c-4248-bbcc-fc30e6f2b308
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 51b8d3b31c92006c4f5b91a874bbb9d66ffa0b1b
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72561495"
---
# <a name="iscriptscriptlet-getsimpleeventname"></a>IScriptScriptlet::GetSimpleEventName
スクリプトレットに関連付けられている単純なイベント名を返します。 これは、空白が含まれていない単一の単語の名前です。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetSimpleEventName(  
   BSTR               *pbstr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstr`  
 入出力@No__t_0 オブジェクトに関連付けられている単純なイベント名を格納するバッファー。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IScriptScriptlet インターフェイス](../../winscript/reference/iscriptscriptlet-interface.md)