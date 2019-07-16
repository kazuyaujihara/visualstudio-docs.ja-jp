---
title: IDiaSymbol::get_baseDataOffset |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: bb2ff5ed-9293-4c37-9741-654058b571c5
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7496cb318abdc194ff832d4fbdbaf570e5cc68e7
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "62572875"
---
# <a name="idiasymbolgetbasedataoffset"></a>IDiaSymbol::get_baseDataOffset
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

基本データ オフセットを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT get_baseDataOffset(   
   DWORD* pRetVal);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]ポインター、`DWORD`基本データ オフセットを保持しています。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
