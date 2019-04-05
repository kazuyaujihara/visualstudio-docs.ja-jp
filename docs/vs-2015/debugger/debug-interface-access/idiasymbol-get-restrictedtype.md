---
title: IDiaSymbol::get_restrictedType |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: c48b00a6-26b0-47b0-b824-fe44dedbc756
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 332ed15c4a6bb9a759e18e1df1e7c456c1303754
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58974671"
---
# <a name="idiasymbolgetrestrictedtype"></a>IDiaSymbol::get_restrictedType
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

指定するかどうか、`this`ポインターがフラグが設定された制限付きとします。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT get_restrictedType(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]ポインターを`BOOL`を指定するかどうか、`this`ポインターがフラグが設定された制限付きとします。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
