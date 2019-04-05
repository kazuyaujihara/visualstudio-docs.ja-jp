---
title: Idiasymbol::get_reference |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_reference method
ms.assetid: 6a97cb74-6a14-41fd-8e24-2a42d7a1e529
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3f76b95b2ef4cafedf9c65f68dc056b49db94176
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58976906"
---
# <a name="idiasymbolgetreference"></a>IDiaSymbol::get_reference
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

ポインター型が参照するかどうかを指定するフラグを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_reference (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]返します`TRUE`ポインター型が; の参照を返しますそれ以外の場合、`FALSE`します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
>  戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
