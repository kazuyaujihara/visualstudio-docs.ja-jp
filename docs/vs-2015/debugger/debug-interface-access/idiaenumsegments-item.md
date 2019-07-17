---
title: Idiaenumsegments::item |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments::Item method
ms.assetid: ee44dd55-39a0-4b7b-97ff-2e1226eeb2bd
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1e69c8123af3ac9061141058d5eb41178e5cd0e4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68189895"
---
# <a name="idiaenumsegmentsitem"></a>IDiaEnumSegments::Item
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

インデックスを使用してセグメントを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT Item (   
   DWORD         index,  
   IDiaSegment** segment  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 インデックス  
 [in]インデックス、 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)を取得するオブジェクト。 インデックスは 0 ~ の範囲内で、 `count`-1 の場合、`count`によって返される、 [idiaenumsegments::get_count](../../debugger/debug-interface-access/idiaenumsegments-get-count.md)メソッド。  
  
 segment  
 [out]返します、 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)必要なセグメントを表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)
