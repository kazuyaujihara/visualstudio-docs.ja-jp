---
title: Idiasymbol::get_length |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_length method
ms.assetid: cc62f028-d195-4fbf-93bc-10b08bef52d2
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2942c69908348b13bb2a682471ca82cff850830d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973596"
---
# <a name="idiasymbolgetlength"></a>IDiaSymbol::get_length
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

この記号によって表されるオブジェクトによって使用されるメモリのバイトまたはビット数を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_length (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]この記号によって表されるオブジェクトによって使用されるメモリのビットまたはバイト数を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
>  戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。  
  
## <a name="remarks"></a>Remarks  
 場合、 [LocationType 列挙型](../../debugger/debug-interface-access/locationtype.md)のシンボルは`LocIsBitField`、このメソッドによって返される文字数は bits では、文字数はそれ以外の場合、その他のすべての場所の種類のバイト数でします。  
  
## <a name="example"></a>例  
  
```cpp#  
IDiaSymbol* pSymbol;  
ULONGLONG   length;  
pSymbol->get_length( &length );  
```  
  
## <a name="requirements"></a>必要条件  
  
|必要条件|説明|  
|-----------------|-----------------|  
|ヘッダー:|Dia2.h|  
|バージョン:|DIA SDK v7.0|  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 列挙型](../../debugger/debug-interface-access/locationtype.md)
