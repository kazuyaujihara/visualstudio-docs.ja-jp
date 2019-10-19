---
title: 'IJsDebugDataTarget:: WriteMemory メソッド |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.WriteMemory
apilocation:
- jscript9diag.dll
ms.assetid: 0d3c04c3-9ef8-4842-a145-3d29bca75062
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 33cd23ad784e222f770dfd5c0e7c2d775aa55e42
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572420"
---
# <a name="ijsdebugdatatargetwritememory-method"></a>IJsDebugDataTarget::WriteMemory メソッド
ターゲット プロセスのメモリを読み取ります。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT WriteMemory(  
   UINT64 address,  
   const BYTE *pMemory,  
   DWORD size  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `address`  
 [入力] ターゲット プロセスのメモリの書き込み元のベース アドレス。  
  
 `pMemory`  
 [入力] 指定したプロセスのアドレス空間に書き込むデータ。  
  
 `size`  
 [入力] プロセスに書き込むバイト数。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="remarks"></a>Remarks  
 データ転送が行われる前に、ベース アドレスのすべてのデータと指定したサイズのメモリに書き込みアクセスが可能であることがシステムによって確認され、可能でない場合、この関数によって E_JsDEBUG_INVALID_MEMORY_ADDRESS エラーが発生します。  
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [IJsDebugDataTarget インターフェイス](../../winscript/reference/ijsdebugdatatarget-interface.md)