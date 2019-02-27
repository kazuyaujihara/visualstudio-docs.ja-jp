---
title: IDiaSymbol::get_acceleratorPointerTags |Microsoft Docs
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
ms.openlocfilehash: c1724ee3e81ac00ed048f323105842361ec22bc7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56607955"
---
# <a name="idiasymbolgetacceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
C++ AMP のアクセラレータのスタブ関数に対応するすべてのアクセラレータ ポインター タグ値を返します。

## <a name="syntax"></a>構文

```C++
HRESULT get_acceleratorPointerTags(
   DWORD          cnt,
   DWORD*         pcnt,
   DWORD*         pPointerTags);
```

#### <a name="parameters"></a>パラメーター
 `cnt`

[in]出力配列のサイズ`pPointerTags`します。

 `pcnt`

[out]C++ AMP のアクセラレータのスタブ関数でアクセラレータ ポインター タグの数。

 `pPointerTags`

[out]A `DWORD` C++ AMP のアクセラレータのスタブ関数でアクセラレータ ポインター タグの値が入力配列のポインター。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

## <a name="remarks"></a>解説
 このメソッドが、 `IDiaSymbol` C++ AMP のアクセラレータのスタブ関数に対応するインターフェイス。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)