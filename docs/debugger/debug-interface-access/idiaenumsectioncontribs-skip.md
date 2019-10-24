---
title: 'IDiaEnumSectionContribs:: Skip |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::Skip method
ms.assetid: 7471a178-5134-41b2-80a6-51ff96abe916
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cb371d841c10b64895400f66bf73159f27d68ec1
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744264"
---
# <a name="idiaenumsectioncontribsskip"></a>IDiaEnumSectionContribs::Skip
列挙シーケンス内の指定された数のセクション投稿をスキップします。

## <a name="syntax"></a>構文

```C++
HRESULT Skip( 
   ULONG celt
);
```

#### <a name="parameters"></a>パラメーター
 `celt`

からスキップする列挙シーケンス内のセクションの貢献数。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、スキップするセクションの投稿がこれ以上ない場合は `S_FALSE` を返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)