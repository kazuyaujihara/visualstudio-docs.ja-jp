---
title: IDebugDocumentTextExternalAuthor::GetPathName |Microsoft Docs
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
ms.openlocfilehash: 5739e7cb0cb12661ee5683051fb7b687e62dfde4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62978755"
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
 [out]完全なパスとファイル名を含む文字列します。  
  
 `pfIsOriginalFile`  
 [out]パスとファイル名が参照するかどうかを示すブール値、元のドキュメントにします。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_FAIL`|ソース ファイルを作成または決定できません。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、ドキュメントの完全なパスとファイル名を返します。  
  
 場合`pfIsOriginalFile`FALSE、パスとファイル名は、`pbstrLongName`新しく作成された一時ファイルを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentTextExternalAuthor インターフェイス](../../winscript/reference/idebugdocumenttextexternalauthor-interface.md)