---
title: 'IDiaSymbol:: get_acceleratorPointerTags |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f36b4bf9fdd362f4941e33745d59d481a473c607
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741115"
---
# <a name="idiasymbolget_acceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
C++ AMP accelerator スタブ関数に対応するすべてのアクセラレータポインタータグ値を返します。

## <a name="syntax"></a>構文

```C++
HRESULT get_acceleratorPointerTags(
   DWORD          cnt,
   DWORD*         pcnt,
   DWORD*         pPointerTags);
```

#### <a name="parameters"></a>パラメーター
 `cnt`

から出力配列 `pPointerTags` のサイズ。

 `pcnt`

入出力C++ AMP accelerator スタブ関数内のアクセラレータポインタータグの数。

 `pPointerTags`

入出力C++ AMP accelerator スタブ関数のアクセラレータポインターのタグ値を格納する `DWORD` 配列ポインター。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、`S_FALSE` またはエラーコードを返します。

## <a name="remarks"></a>Remarks
 このメソッドは、 C++ AMP accelerator スタブ関数に対応する `IDiaSymbol` インターフェイスで呼び出されます。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)