---
title: IDebugApplication::CreateApplicationNode |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.CreateApplicationNode
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::CreateApplicationNode
ms.assetid: 1a1414f6-df14-4c56-b39a-8384cf16174a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 02a15a67d8f8b6171e9f5893c7f8cd15f79776b1
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144785"
---
# <a name="idebugapplicationcreateapplicationnode"></a>IDebugApplication::CreateApplicationNode
特定のドキュメント プロバイダーに関連付けられたアプリケーションの新しいノードを作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CreateApplicationNode(  
   IDebugApplicationNode**  ppdanNew  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppdanNew`  
 [out]このドキュメントのプロバイダーに関連付けられたアプリケーション ノード。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 親ノードにアタッチされるまでは、新しいアプリケーション ノードは表示されません。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplication インターフェイス](../../winscript/reference/idebugapplication-interface.md)