---
title: Ijsdebugdatatarget::readbstr メソッド |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.ReadBSTR
apilocation:
- jscript9diag.dll
ms.assetid: 4b571db7-04b9-42a0-9a3e-310ac9d0e659
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2e821893318cfe1d8f0b4239a077fc91c26be47f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62582343"
---
# <a name="ijsdebugdatatargetreadbstr-method"></a>IJsDebugDataTarget::ReadBSTR メソッド
デバッグ対象から BSTR を読み取ります。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT ReadBSTR(  
   UINT64 address,  
   BSTR *pString  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `address`  
 [入力] 読み取り元のアドレス。  
  
 `pString`  
 [出力] デバッグ対象から読み取った BSTR。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="remarks"></a>Remarks  
 アドレスが有効でない場合は E_JsDEBUG_INVALID_MEMORY_ADDRESS を返します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** jscript9diag.h です  
  
## <a name="see-also"></a>関連項目  
 [IJsDebugDataTarget インターフェイス](../../winscript/reference/ijsdebugdatatarget-interface.md)