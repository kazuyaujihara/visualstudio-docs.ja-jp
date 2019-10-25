---
title: 'IDiaEnumFrameData:: Item |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::Item method
ms.assetid: 2761a72d-1868-4f5b-a32e-c2a1d9358c91
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c15f395e7f4aa576c5f69b0f1c61f37ca808fb6
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744610"
---
# <a name="idiaenumframedataitem"></a>IDiaEnumFrameData::Item
インデックスを使って、フレームデータ要素を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Item ( 
   DWORD           index,
   IDiaFrameData** section
);
```

#### <a name="parameters"></a>パラメーター
 インデックス

から取得する[IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)オブジェクトのインデックス。 インデックスは 0 ~ `count`-1 の範囲にあり、`count` は[IDiaEnumFrameData:: get_Count](../../debugger/debug-interface-access/idiaenumframedata-get-count.md)メソッドによって返されます。

 section

入出力目的のフレームデータ要素を表す[IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)