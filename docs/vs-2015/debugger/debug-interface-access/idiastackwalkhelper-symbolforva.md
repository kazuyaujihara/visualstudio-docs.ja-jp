---
title: Idiastackwalkhelper::symbolforva |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper::symbolForVA method
ms.assetid: 8dd9455d-d44c-4dd6-a0aa-31131cbea2aa
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5ed714501f18b0c1ab771556a56a6ca3bbc061d8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68150043"
---
# <a name="idiastackwalkhelpersymbolforva"></a>IDiaStackWalkHelper::symbolForVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

指定した仮想アドレスを表すシンボルを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT symbolForVA(   
   ULONGLONG     va,  
   IDiaSymbol**  ppSymbol  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `va`  
 [in]要求されたシンボルが含まれている仮想アドレス。 シンボルがある必要があります、 `SymTagFunctionType` (からの値、 [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)列挙型)。  
  
 `ppSymbol`  
 [out][IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)指定のアドレスにあるシンボルを表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
