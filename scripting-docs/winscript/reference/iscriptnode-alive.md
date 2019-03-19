---
title: IScriptNode::Alive |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.Alive
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::Alive
ms.assetid: d2755c83-e9b9-4c0a-acb7-25b554fc9fe8
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: da0a55d26b5ab643670ba7ed51e576eeb89d8b98
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58159219"
---
# <a name="iscriptnodealive"></a>IScriptNode::Alive
オブジェクトがまだアクティブかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Alive();  
```  
  
#### <a name="parameters"></a>パラメーター  
 メソッドには、パラメーターはありません。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|スクリプトのノードはアクティブです。|  
  
## <a name="remarks"></a>Remarks  
 オブジェクトがアクティブでない場合、コンポーネント オブジェクト モデル (COM) は、このメソッド呼び出しのマーシャ リング プロキシからエラーを返します。  
  
## <a name="see-also"></a>関連項目  
 [IScriptNode インターフェイス](../../winscript/reference/iscriptnode-interface.md)