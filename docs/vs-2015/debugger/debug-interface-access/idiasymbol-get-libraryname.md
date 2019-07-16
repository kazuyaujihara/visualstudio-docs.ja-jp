---
title: Idiasymbol::get_libraryname |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_libraryName method
ms.assetid: d04ddd9a-812d-46e4-bd39-28bdf3edfb70
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cdab8fdff421da751f3813789a6dee8b5b640771
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64810809"
---
# <a name="idiasymbolgetlibraryname"></a>IDiaSymbol::get_libraryName
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

オブジェクトの読み込み元のライブラリまたはオブジェクトのファイルのファイル名を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_libraryName (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]オブジェクトの読み込み元のライブラリまたはオブジェクトのファイルのファイル名を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
> 戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
