---
title: 'IDebugDocumentHost:: GetPathName |Microsoft Docs'
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
ms.openlocfilehash: 33ebcde4cf1db28e199f13fae720374bd1b64763
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72569283"
---
# <a name="idebugdocumenthostgetpathname"></a>IDebugDocumentHost::GetPathName
ドキュメントのソースファイルの完全パスとファイル名を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetPathName(  
   BSTR*  pbstrLongName,  
   BOOL*  pfIsOriginalFile  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstrLongName`  
 入出力長い名前を含む文字列。  
  
 `pfIsOriginalFile`  
 入出力@No__t_0 がドキュメントの元のファイルを参照している場合は true、それ以外の場合は false を示すフラグ。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_FAIL`|ソースファイルを作成または特定できません。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、ドキュメントのソースファイルの完全パスとファイル名を返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentHost インターフェイス](../../winscript/reference/idebugdocumenthost-interface.md)