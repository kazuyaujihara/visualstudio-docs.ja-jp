---
title: IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 024ccd78-5867-4ca7-bc26-548758e9ac53
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 673ca8137244fed933df0be3fa0221115951a9c1
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56618108"
---
# <a name="idiasymbolfindsymbolsbyrvaforacceleratorpointertag"></a>IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag
対応するタグの値を指定すると、このメソッドは、指定の相対仮想アドレスにある場合は、このスタブ関数に含まれているシンボルの列挙体を返します。

## <a name="syntax"></a>構文

```C++
HRESULT findSymbolsByRVAForAcceleratorPointerTag (
   DWORD             tagValue,
   DWORD             rva,
   IDiaEnumSymbols** ppResult);
```

#### <a name="parameters"></a>パラメーター
 `tagValue`

[in]Pointee シンボル レコードを検出するポインターのタグ値。

 `rva`

[in]指定したタグ値を持つ pointee 変数に対応するシンボルをフィルター処理に使用される rva を示します。

 `ppResult`

[out]ポインター、`IDiaEnumSymbols`結果で初期化されるインターフェイス ポインター。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

## <a name="remarks"></a>解説
 のみこのメソッドを呼び出し、`IDiaSymbol`アクセラレータのスタブ関数に対応するインターフェイス。

## <a name="see-also"></a>参照
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)