---
title: Idiasymbol::get_unalignedtype |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_unalignedType method
ms.assetid: fdcb38fb-490e-4d15-b4e5-3770043a366c
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ddd5d6a99f0d5e2f0eb3bab87bbe7805b7d8588a
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63400077"
---
# <a name="idiasymbolgetunalignedtype"></a>IDiaSymbol::get_unalignedType
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

ユーザー定義データ型が整列されていないかどうかを指定するフラグを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_unalignedType (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]返します`TRUE`、ユーザー定義データ型がアラインされていない、それ以外の場合は、返す`FALSE`します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
> 戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
