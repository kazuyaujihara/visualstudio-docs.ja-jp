---
title: 'IActiveScriptSiteDebug:: GetRootApplicationNode |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteDebug.GetRootApplicationNode
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteDebug::GetRootApplicationNode
ms.assetid: 2393f566-6b97-47c0-8041-4dd7e3b1d3a3
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b19ed10178d03be0b96393ad08f1eab88ce40329
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72570063"
---
# <a name="iactivescriptsitedebuggetrootapplicationnode"></a>IActiveScriptSiteDebug::GetRootApplicationNode
スクリプトドキュメントを追加する必要があるアプリケーションノードを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetRootApplicationNode(  
   IDebugApplicationNode**  ppdanRoot  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppdanRoot`  
 入出力スクリプトドキュメントを保持するデバッグアプリケーションノード。 `NULL` の可能性があります。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、スクリプトドキュメントを追加する必要があるアプリケーションノードを返します。 スクリプトドキュメントを最上位に配置する必要がある場合、メソッドは `ppdanRoot` に対して `NULL` を返すことができます。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSiteDebug インターフェイス](../../winscript/reference/iactivescriptsitedebug-interface.md)