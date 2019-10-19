---
title: 'IDebugDocumentTextExternalAuthor:: GetPathName |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentTextExternalAuthor.GetPathName
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentTextExternalAuthor::GetPathName
ms.assetid: 445152a1-9cf8-402e-93d6-3d4bf2b81d17
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e876b41ce1bde4defffd11267c6665f9d57da077
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575963"
---
# <a name="idebugdocumenttextexternalauthorgetpathname"></a>IDebugDocumentTextExternalAuthor::GetPathName
ドキュメントの完全なパスとファイル名を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetPathName(  
   BSTR*  pbstrLongName,  
   BOOL*  pfIsOriginalFile  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstrLongName`  
 入出力完全なパスとファイル名を含む文字列。  
  
 `pfIsOriginalFile`  
 入出力パスとファイル名が元のドキュメントを参照しているかどうかを示すブール値。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_FAIL`|ソースファイルを作成または特定できません。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、ドキュメントの完全なパスとファイル名を返します。  
  
 @No__t_0 が FALSE の場合、`pbstrLongName` 内のパスとファイル名は、新しく作成された一時ファイルを参照します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentTextExternalAuthor インターフェイス](../../winscript/reference/idebugdocumenttextexternalauthor-interface.md)