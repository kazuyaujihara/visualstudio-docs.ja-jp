---
title: DiaAddressMapEntry |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DiaAddressMapEntry enumeration
ms.assetid: 5d0ae226-981d-4541-a801-fc4993fe663b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 54b326116b1e1b677a997b264cf0c168a93febb0
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745264"
---
# <a name="diaaddressmapentry"></a>DiaAddressMapEntry
アドレスマップのエントリを記述します。

## <a name="syntax"></a>構文

```C++
struct DiaAddressMapEntry {
    DWORD rva,
    DWORD rvaTo
};
```

## <a name="elements"></a>Elements
イメージ A の相対仮想アドレス (RVA) を `rva` します。

`rvaTo`、イメージ B のにマップされる相対仮想アドレス `rva` です。

## <a name="remarks"></a>Remarks
アドレスマップは、1つのイメージレイアウト (A) から別のイメージレイアウト (B) への変換を提供します。 @No__t_1 によって並べ替えられた `DiaAddressMapEntry` 構造体の配列は、アドレスマップを定義します。

イメージ A のアドレスをアドレスに変換するには、イメージ B で次の手順を実行し `addrB` ます。 `addrA`

1. マップで、`addrA` 以下の最大 `rva` を持つエントリ `e` を検索します。

2. `delta = addrA - e.rva` を設定します。

3. `addrB = e.rvaTo + delta` を設定します。

    @No__t_0 構造体の配列は、 [IDiaAddressMap:: set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)メソッドに渡されます。

## <a name="requirements"></a>［要件］
ヘッダー: dia2

## <a name="see-also"></a>関連項目
- [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)
