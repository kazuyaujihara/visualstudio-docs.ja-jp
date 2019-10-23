---
title: 'IScriptNode:: Alive |Microsoft Docs'
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
ms.openlocfilehash: b7e0216824506ee942b42a42d5c3c4475f63f9e2
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573622"
---
# <a name="iscriptnodealive"></a>IScriptNode::Alive
オブジェクトがまだアクティブであるかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Alive();  
```  
  
#### <a name="parameters"></a>パラメーター  
 メソッドはパラメーターを受け取りません。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|スクリプトノードはまだアクティブです。|  
  
## <a name="remarks"></a>Remarks  
 オブジェクトがアクティブでない場合、コンポーネントオブジェクトモデル (COM) は、このメソッドの呼び出しに対してマーシャリングプロキシからエラーを返します。  
  
## <a name="see-also"></a>関連項目  
 [IScriptNode インターフェイス](../../winscript/reference/iscriptnode-interface.md)