---
title: Idiasymbol::get_addresssection |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_addressSection method
ms.assetid: fe80d479-3bb5-4f55-9b62-1bd58d0a60ce
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cff7d51b1e07c26b9c5d88ce81301f4ca8c50d93
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58962320"
---
# <a name="idiasymbolgetaddresssection"></a>IDiaSymbol::get_addressSection
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

アドレス場所のセクションの一部を取得します。 使用する場合、 [LocationType 列挙型](../../debugger/debug-interface-access/locationtype.md)に設定されている`LocIsStatic`します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_addressSection (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]アドレス場所のセクションの一部を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
>  戻り値`S_FALSE`プロパティがシンボルを使用できないことを意味します。  
  
## <a name="remarks"></a>Remarks  
 静的メンバーを外部 DLL 内にある、このメソッドによって返されるセクションが 0 に仮想メンバーのアドレスを取得するのには、このメソッドを利用。 仮想アドレスは有効な場合にのみ、 [idiasession::put_loadaddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)メソッドで、 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)インターフェイスは、DLL の読み込みアドレスを指定する 0 以外のパラメーターで呼び出されました。  
  
 アドレスのオフセットの部分を取得する、 [idiasymbol::get_addressoffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)メソッド。  
  
## <a name="requirements"></a>必要条件  
  
|必要条件|説明|  
|-----------------|-----------------|  
|ヘッダー:|Dia2.h|  
|バージョン:|DIA SDK v7.0|  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 列挙型](../../debugger/debug-interface-access/locationtype.md)
