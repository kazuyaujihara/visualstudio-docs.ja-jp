---
title: 'IDiaEnumSegments:: Item |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments::Item method
ms.assetid: ee44dd55-39a0-4b7b-97ff-2e1226eeb2bd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 101821e3c00d3aeac9b131ee5a11ab9a01e090a9
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744180"
---
# <a name="idiaenumsegmentsitem"></a>IDiaEnumSegments::Item
インデックスを使ってセグメントを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Item ( 
   DWORD         index,
   IDiaSegment** segment
);
```

#### <a name="parameters"></a>パラメーター
 インデックス

から取得する[IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)オブジェクトのインデックス。 インデックスは 0 ~ `count`-1 の範囲にあり、`count` は[IDiaEnumSegments:: get_Count](../../debugger/debug-interface-access/idiaenumsegments-get-count.md)メソッドによって返されます。

 segment

入出力目的のセグメントを表す[IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)
- [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)