---
title: 'IDebugDocumentHost:: GetFileName |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHost.GetFileName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentHost::GetFileName
ms.assetid: b814a848-8a3d-468d-9282-c5c0354b22a1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ff2ad2e4ab419f1e503da072aaa550f3cb7cf0e
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72569395"
---
# <a name="idebugdocumenthostgetfilename"></a>IDebugDocumentHost::GetFileName
パス情報を含まないドキュメントの名前を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetFileName(  
   BSTR*  pbstrShortName  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstrShortName`  
 入出力ドキュメントの短い名前を格納している文字列。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、パス情報のないドキュメントの短い名前を返します。 短い名前は、通常、[名前**を付けて保存...** ] ダイアログボックスなどの状況で使用されます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentHost インターフェイス](../../winscript/reference/idebugdocumenthost-interface.md)