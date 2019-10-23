---
title: 'IDiaSymbol:: findSymbolsByRVAForAcceleratorPointerTag |Microsoft Docs'
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
ms.openlocfilehash: f0d05946db816e6bd209e364e11d5091163941a4
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741156"
---
# <a name="idiasymbolfindsymbolsbyrvaforacceleratorpointertag"></a>IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag
対応するタグ値が指定されている場合、このメソッドは、指定された相対仮想アドレスで、このスタブ関数に含まれるシンボルの列挙体を返します。

## <a name="syntax"></a>構文

```C++
HRESULT findSymbolsByRVAForAcceleratorPointerTag (
   DWORD             tagValue,
   DWORD             rva,
   IDiaEnumSymbols** ppResult);
```

#### <a name="parameters"></a>パラメーター
 `tagValue`

からPointee シンボルレコードが存在するポインタータグ値。

 `rva`

から指定されたタグ値を持つ pointee 変数に対応するシンボルをフィルター処理するために使用される rva。

 `ppResult`

入出力結果を使用して初期化される `IDiaEnumSymbols` インターフェイスポインターへのポインター。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、`S_FALSE` またはエラーコードを返します。

## <a name="remarks"></a>Remarks
 このメソッドは、アクセラレータスタブ関数に対応する `IDiaSymbol` インターフェイスでのみ呼び出します。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)