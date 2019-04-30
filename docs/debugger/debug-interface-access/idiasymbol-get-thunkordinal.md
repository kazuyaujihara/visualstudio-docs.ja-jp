---
title: Idiasymbol::get_thunkordinal |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_thunkOrdinal method
ms.assetid: 4b28d78a-1974-4d8a-8bb7-781bf630f2f4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6dadfff62502af59652e9113553e13b4942c540f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63401339"
---
# <a name="idiasymbolgetthunkordinal"></a>IDiaSymbol::get_thunkOrdinal
関数のサンクの型を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_thunkOrdinal ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]値を返します、 [THUNK_ORDINAL 列挙型](../../debugger/debug-interface-access/thunk-ordinal.md)関数のサンクの型を指定する列挙体。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。

## <a name="remarks"></a>Remarks
 このプロパティは有効な場合にのみとしてシンボルを[SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)の値`SymTagThunk`します。

 「サンク」は、32 ビット メモリ アドレス空間 (フラットのアドレス空間とも呼ばれます) と (セグメント化されたアドレス空間と呼ばれます)、16 ビットのアドレス空間を変換するコードです。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [THUNK_ORDINAL 列挙型](../../debugger/debug-interface-access/thunk-ordinal.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)