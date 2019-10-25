---
title: 'IDiaEnumSectionContribs:: Item |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::Item method
ms.assetid: 63a28f23-0ca0-44a7-b11b-ca0206d642a0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d021b5016bd0e0039f2bf175102dc44f04dabaab
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744292"
---
# <a name="idiaenumsectioncontribsitem"></a>IDiaEnumSectionContribs::Item
インデックスを使ってセクションの貢献度を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Item ( 
   DWORD                index,
   IDiaSectionContrib** section
);
```

#### <a name="parameters"></a>パラメーター
 インデックス

から取得する[IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)オブジェクトのインデックス。 インデックスは 0 ~ `count`-1 の範囲にあり、`count` は[IDiaEnumSectionContribs:: get_Count](../../debugger/debug-interface-access/idiaenumsectioncontribs-get-count.md)メソッドによって返されます。

 section

入出力目的のセクションの貢献度を表す[IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumSectionContribs::get_Count](../../debugger/debug-interface-access/idiaenumsectioncontribs-get-count.md)
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)