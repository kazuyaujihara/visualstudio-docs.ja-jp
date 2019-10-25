---
title: 'IDiaEnumSectionContribs:: get__NewEnum |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::get__NewEnum method
ms.assetid: a16ee92f-3081-416a-98f6-ce6bc8288a8b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4bbd4e2d818fe2e795b03536b514297a05771e92
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744308"
---
# <a name="idiaenumsectioncontribsget__newenum"></a>IDiaEnumSectionContribs::get__NewEnum
この列挙子の <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> バージョンを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get__NewEnum ( 
   IUnknown** pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 の場合は、

入出力この列挙子の <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> バージョンを表す `IUnknown` インターフェイスを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)