---
title: IDiaSymbol::get_isAcceleratorPointerTagLiveRange |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d195aec4-6d3c-42e0-88a5-3d463539f0b8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c8bf20f43fcc8da48a6e1ec1dfd0f65b14f8ad86
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62836903"
---
# <a name="idiasymbolgetisacceleratorpointertagliverange"></a>IDiaSymbol::get_isAcceleratorPointerTagLiveRange
シンボルに対応するかどうかを示すフラグを取得、*定義範囲シンボル*C++ AMP のアクセラレータのコンパイルされたコードでポインター変数のタグの要素。 定義の範囲のシンボルは、アドレスの範囲の変数の場所です。

## <a name="syntax"></a>構文

```C++
HRESULT get_isAcceleratorPointerTagLiveRange(
   BOOL* pFlag);
```

#### <a name="parameters"></a>パラメーター
 `pFlag`

[out]ポインターを`BOOL`シンボルが定義の範囲のシンボルに対応するかどうかを示します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
