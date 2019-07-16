---
title: Idiastackframe::get_rawlvarinstancevalue |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_rawLVarInstanceValue method
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c8ff78c38ad077084b3dea9c96e3251ffddb2206
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62573015"
---
# <a name="idiastackframegetrawlvarinstancevalue"></a>IDiaStackFrame::get_rawLVarInstanceValue
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

このメソッドは、実際のバイト数として指定されたローカル変数の値を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_rawLVarInstanceValue(  
   IDiaLVarInstance* pInstance,  
   DWORD             cbDataMax,  
   DWORD*            pcbData,  
   BYTE*             pbData  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pInstance`  
 [in]`IDiaLVarInstance`の値を取得するローカル変数のインスタンスを表すオブジェクト。  
  
 `cbDataMax`  
 [in]バッファー内のバイトの最大数が指す`pbData`します。 これができる 8 バイトの最大値 (`sizeof(ULONGLONG)`)。  
  
 `pcbData`  
 [out]実際、バッファーに格納されるバイト数を返します。  
  
 `pbData`  
 [out]データと共に格納するバッファー。 これは `NULL` にすることはできません。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
