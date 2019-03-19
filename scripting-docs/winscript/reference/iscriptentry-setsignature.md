---
title: IScriptEntry::SetSignature |Microsoft Docs
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
ms.openlocfilehash: 42740a0e6261317443b8c9cc23559a2f92f66540
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58150609"
---
# <a name="iscriptentrysetsignature"></a>IScriptEntry::SetSignature
セットの情報を入力する、`IScriptEntry`関数オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetSignature(  
   ITypeInfo          *pti  
   ULONG              iMethod  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pti`  
 [in]型情報。  
  
 `iMethod`  
 [in]内のメソッドのインデックス、`ITypeInfo`オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 使用して型情報を設定する`IScriptEntry::SetSignature`または[IScriptNode::CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md)します。 関数の内部表現に基づくエントリによって、型情報を生成こともできます。  
  
## <a name="see-also"></a>関連項目  
 [IScriptEntry インターフェイス](../../winscript/reference/iscriptentry-interface.md)