---
title: IDiaSymbol::get_isPointerToDataMember |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: ef17c737-242e-43e8-b7e1-2c3bc58cfcef
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ca44d11dfcec717e37a9bc13a2d87f9f5a94ede3
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "68155876"
---
# <a name="idiasymbolgetispointertodatamember"></a>IDiaSymbol::get_isPointerToDataMember
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

このシンボルがデータ メンバーへのポインターであるかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT get_isPointerToDataMember(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]ポインターを`BOOL`シンボルは、データ メンバーへのポインターであるかどうかを指定します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
