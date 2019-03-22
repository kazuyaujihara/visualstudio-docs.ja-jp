---
title: IDebugDocumentHost::GetPathName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHost.GetPathName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentHost::GetPathName
ms.assetid: 8abe2a86-e467-4ac9-8ccb-8761141bfa0d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 09e36411cdd378e78ac3bc59df5330eb8ecb47b6
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58160577"
---
# <a name="idebugdocumenthostgetpathname"></a>IDebugDocumentHost::GetPathName
ドキュメントのソース ファイルの完全なパスとファイル名を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetPathName(  
   BSTR*  pbstrLongName,  
   BOOL*  pfIsOriginalFile  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstrLongName`  
 [out]長い名前を含む文字列。  
  
 `pfIsOriginalFile`  
 [out]フラグが true の場合`pbstrLongName`それ以外の場合は false、ドキュメントの元のファイルを参照します。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_FAIL`|ソース ファイルがありませんを作成または確認できます。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、ドキュメントのソース ファイルの完全なパスとファイル名を返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentHost インターフェイス](../../winscript/reference/idebugdocumenthost-interface.md)