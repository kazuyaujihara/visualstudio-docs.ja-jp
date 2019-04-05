---
title: IDiaPropertyStorage::ReadBOOL |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadBOOL
ms.assetid: ad1822db-4572-48f7-9919-f8137f6701f2
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 64eee421a5ed5bd46a64b51694d913a4f2dc4d41
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977251"
---
# <a name="idiapropertystoragereadbool"></a>IDiaPropertyStorage::ReadBOOL
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

読み取り`BOOL`プロパティ セット内の値。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT ReadBOOL (   
   PROPID id,  
   BOOL*  pValue  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `id`  
 [in]読み取るプロパティの識別子 (`PROPID`として WTypes.h で定義されている、 `ULONG`)。  
  
 `pValue`  
 [out]プロパティ値を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外の場合はエラー コードを返します。 返します`E_INVALIDARG`型のプロパティがない場合`BOOL`します。  
  
## <a name="remarks"></a>Remarks  
 一貫性のある結果は、解釈、`BOOL`値の 0 以外の値が実行されるように`TRUE`0 は`FALSE`します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
