---
title: Iprocessdebugmanager::createdebugdocumenthelper |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IProcessDebugManager.CreateDebugDocumentHelper
apilocation:
- pdm.dll
helpviewer_keywords:
- IProcessDebugManager::CreateDebugDocumentHelper
ms.assetid: d644e192-1bcc-4768-a91e-239cd920adcd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 38de1e828ccd1715fb83cc76c06ba837818d2af0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63002352"
---
# <a name="iprocessdebugmanagercreatedebugdocumenthelper"></a>IProcessDebugManager::CreateDebugDocumentHelper
このアプリケーションの新しいデバッグ ドキュメント ヘルパーを作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CreateDebugDocumentHelper(  
   IUnknown*               punkOuter,  
   IDebugDocumentHelper**  pddh  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `punkOuter`  
 [in]集計する場合は、返されたオブジェクト`punkOuter`制御へのインターフェイス ポインターが`IUnknown`します。 それ以外の場合、null ポインターになります。  
  
 `pddh`  
 [out]このアプリケーションのデバッグ ドキュメント ヘルパー オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、このアプリケーションの新しいデバッグ ドキュメント ヘルパーを作成します。  
  
## <a name="see-also"></a>関連項目  
 [IProcessDebugManager インターフェイス](../../winscript/reference/iprocessdebugmanager-interface.md)