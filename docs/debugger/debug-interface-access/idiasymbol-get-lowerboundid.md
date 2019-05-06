---
title: Idiasymbol::get_lowerboundid |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_lowerBoundId method
ms.assetid: 12ce98e9-a225-4947-88c9-5fda39dd67e4
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d0e84f50ce73fded7809478441e88649ff4f1d82
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63399196"
---
# <a name="idiasymbolgetlowerboundid"></a>IDiaSymbol::get_lowerBoundId
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

FORTRAN 配列の次元の下限の境界のシンボルの識別子を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_lowerBoundId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]FORTRAN 配列の次元の下限の境界を表すシンボルのシンボル ID を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
> 戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。  
  
## <a name="remarks"></a>Remarks  
 識別子は、一意としてすべてのシンボルをマークする DIA SDK によって作成された一意の値です。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
