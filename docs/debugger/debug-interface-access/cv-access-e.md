---
title: CV_access_e |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_access_e enumeration
ms.assetid: 33c05d65-abb4-4800-a382-54a3805ea7b0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bbe338ba9d3aa6cbc795606c3fa285526afdfd36
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745369"
---
# <a name="cv_access_e"></a>CV_access_e
メンバー関数と変数の可視性 (アクセスレベル) のスコープを指定します。

## <a name="syntax"></a>構文

```C++
typedef enum CV_access_e {
    CV_private   = 1,
    CV_protected = 2,
    CV_public    = 3
} CV_access_e;
```

## <a name="elements"></a>Elements
CV_private メンバーにはプライベートアクセスがあります。

CV_protected メンバーは、保護されたアクセス権を持っています。

CV_public メンバーにはパブリックアクセスがあります。

## <a name="remarks"></a>Remarks
@No__t_0 アクセス指定子は、クラスのプライベート要素と保護された要素の両方にアクセスできる非メンバー関数によって使用されることが多いため、ここには含まれていません。 [IDiaSymbol:: get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)メソッドを使用して、`SymTagFriend` アクセス権を持つシンボルを検索します。

## <a name="requirements"></a>［要件］
ヘッダー: cvconst. h

## <a name="see-also"></a>関連項目
- [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)
- [IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)
