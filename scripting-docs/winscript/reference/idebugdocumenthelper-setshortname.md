---
title: IDebugDocumentHelper::SetShortName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.SetShortName
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::SetShortName
ms.assetid: 811a444b-0ea4-4374-9d4c-4f7713bdd1ff
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 84cab7872272b08e12c532e6c07b4afb741a53c3
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58158972"
---
# <a name="idebugdocumenthelpersetshortname"></a>IDebugDocumentHelper::SetShortName
ドキュメントの短い名前を設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetShortName(  
   LPCOLESTR  pszShortName  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszShortName`  
 [in]ドキュメントの短い名前を含む null で終わる文字列。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、ドキュメントの新しい短い名前を設定します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentHelper インターフェイス](../../winscript/reference/idebugdocumenthelper-interface.md)