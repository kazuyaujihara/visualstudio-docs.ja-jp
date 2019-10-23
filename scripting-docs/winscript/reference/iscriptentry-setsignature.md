---
title: 'IScriptEntry:: SetSignature |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.SetSignature
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::SetSignature
ms.assetid: 8513587d-9df2-4621-afe7-56eacbb5e688
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e381e642462fe56e661de9da0d8974dc7bf18b18
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575335"
---
# <a name="iscriptentrysetsignature"></a>IScriptEntry::SetSignature
@No__t_0 関数オブジェクトの型情報を設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetSignature(  
   ITypeInfo          *pti  
   ULONG              iMethod  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pti`  
 から型情報。  
  
 `iMethod`  
 から@No__t_0 オブジェクト内のメソッドインデックス。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 型情報は、`IScriptEntry::SetSignature` または[Iscriptnode:: CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md)を使用して設定します。 型情報は、内部関数表現に基づいてエントリによって生成されることもあります。  
  
## <a name="see-also"></a>関連項目  
 [IScriptEntry インターフェイス](../../winscript/reference/iscriptentry-interface.md)