---
title: 'IActiveScriptSite:: GetLCID |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.GetLCID
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_GetLCID
ms.assetid: 7b4a2dc1-bcf6-4bbf-884e-97b305a28eb7
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 913ca23ac687fdd080a778afb1dcba2e4dcdd6b8
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72570741"
---
# <a name="iactivescriptsitegetlcid"></a>IActiveScriptSite::GetLCID
ホストのユーザーインターフェイスに関連付けられているロケール識別子を取得します。 スクリプトエンジンは識別子を使用して、エンジンによって生成されたエラー文字列およびその他のユーザーインターフェイス要素が適切な言語で表示されるようにします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetLCID(  
    LCID *plcid  // address of variable for language identifier  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `plcid`  
 入出力スクリプトエンジンによって表示されるユーザーインターフェイス要素のロケール識別子を受け取る変数のアドレス。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_NOTIMPL`|このメソッドは実装されていません。 システム定義のロケールを使用します。|  
|`E_POINTER`|無効なポインターが指定されました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドが `E_NOTIMPL` を返す場合は、システム定義のロケール識別子を使用する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)