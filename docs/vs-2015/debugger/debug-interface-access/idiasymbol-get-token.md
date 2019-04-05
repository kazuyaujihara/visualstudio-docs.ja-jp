---
title: Idiasymbol::get_token |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_token method
ms.assetid: 7ee7a9be-a0d8-48e4-9fef-d37b3d6ae4ef
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8dc02dd942ba1436a513980a29073ac55f59d4bf
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973804"
---
# <a name="idiasymbolgettoken"></a>IDiaSymbol::get_token
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

マネージ関数または変数のメタデータ トークンを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_token (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]マネージ関数または変数のメタデータ トークンを返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
>  戻り値`S_FALSE`プロパティがシンボルを使用できないことを意味します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
