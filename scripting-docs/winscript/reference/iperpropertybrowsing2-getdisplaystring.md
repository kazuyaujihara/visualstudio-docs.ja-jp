---
title: IPerPropertyBrowsing2::GetDisplayString |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.GetDisplayString
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::GetDisplayString
ms.assetid: 8f75c6a9-86a9-4e2d-8cb4-74e7b1c0a524
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f6f63db8d9c032b8e880f05d4d21e50fd56c74e2
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58147983"
---
# <a name="iperpropertybrowsing2getdisplaystring"></a>IPerPropertyBrowsing2::GetDisplayString
取得に表示される型は本質的に表示されませんが、返されるテキスト文字列は、プロパティを説明する名前を指定および呼び出し元のユーザー インターフェイスに表示することができます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetDisplayString(  
   DISPID  dispid,  
   BSTR*  pBstr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dispid`  
 [in]表示名を持つが要求されたプロパティの識別子をディスパッチします。  
  
 `pBstr`  
 [out]ポインター、`BSTR`によって識別されたプロパティの表示名を含む`dispID`します。  
  
## <a name="return-value"></a>戻り値  
 有効な返します`HRESULT`、通常`S_OK`します。  
  
## <a name="remarks"></a>Remarks  
 返される文字列は、プロパティの有効な値ではありません。 プロパティの文字列の表示だけになります。  
  
## <a name="see-also"></a>関連項目  
 [IPerPropertyBrowsing2 インターフェイス 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)