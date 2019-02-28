---
title: Idiasymbol::get_targetvirtualaddress |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_targetVirtualAddress method
ms.assetid: a0a5ce72-95f8-443e-bb4b-8c21194faad0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ade3d2d968a7b152c982f34fc03144f21059e007
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635268"
---
# <a name="idiasymbolgettargetvirtualaddress"></a>IDiaSymbol::get_targetVirtualAddress
サンク ターゲットの仮想アドレス (VA) を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_targetVirtualAddress ( 
   ULONGLONG* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]サンク ターゲットの VA を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
>  戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。

## <a name="remarks"></a>解説
 このプロパティは有効な場合にのみとしてシンボルを[SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)の値`SymTagThunk`します。

 「サンク」は、32 ビット メモリ アドレス空間 (フラットのアドレス空間とも呼ばれます) と (セグメント化されたアドレス空間と呼ばれます)、16 ビットのアドレス空間を変換するコードです。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)