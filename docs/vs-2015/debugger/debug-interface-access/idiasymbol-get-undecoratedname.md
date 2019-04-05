---
title: Idiasymbol::get_undecoratedname |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_undecoratedName method
ms.assetid: e49edf25-a51d-4787-bd5b-2bf5af827c8c
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e7870f19bee3dd67f62659c39403b1019d6d1687
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58962485"
---
# <a name="idiasymbolgetundecoratedname"></a>IDiaSymbol::get_undecoratedName
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

C++ の装飾、またはリンケージ、名前の非装飾名を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_undecoratedName (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]C++ の非装飾の名前の装飾名を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
>  戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
