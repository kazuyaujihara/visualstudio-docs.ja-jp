---
title: Idiaenumsectioncontribs::item |Microsoft Docs
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
ms.openlocfilehash: 2cd51bd663087aa04a7ec4e60e5c4291a35d9193
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56646956"
---
# <a name="idiaenumsectioncontribsitem"></a>IDiaEnumSectionContribs::Item
インデックスを使用して、セクションの投稿を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Item ( 
   DWORD                index,
   IDiaSectionContrib** section
);
```

#### <a name="parameters"></a>パラメーター
 インデックス

[in]インデックス、 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)を取得するオブジェクト。 インデックスは 0 ~ の範囲内で、 `count`-1 の場合、`count`によって返される、 [idiaenumsectioncontribs::get_count](../../debugger/debug-interface-access/idiaenumsectioncontribs-get-count.md)メソッド。

 section

[out]返します、 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)店が貢献したセクションの目的を表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumSectionContribs::get_Count](../../debugger/debug-interface-access/idiaenumsectioncontribs-get-count.md)
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)