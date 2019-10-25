---
title: 'IDiaEnumInjectedSources:: Item |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::Item method
ms.assetid: 14846955-7270-451d-91d2-9cb34bb65187
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 91be2f4f437cfeed30b0741d10bf719ba0ed2b71
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744502"
---
# <a name="idiaenuminjectedsourcesitem"></a>IDiaEnumInjectedSources::Item
インデックスを使って挿入されたソースを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Item ( 
   DWORD                index,
   IDiaInjectedSource** injectedSource
);
```

#### <a name="parameters"></a>パラメーター
 インデックス

から取得する[IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)オブジェクトのインデックス。 インデックスは、0 ~ `count`-1 の範囲です。この場合、`count` は[IDiaEnumInjectedSources:: get_Count](../../debugger/debug-interface-access/idiaenuminjectedsources-get-count.md)メソッドによって返されます。

 injectedSource

入出力挿入されたソースを表す[IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)
- [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)