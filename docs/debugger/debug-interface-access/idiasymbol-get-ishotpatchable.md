---
title: Idiasymbol::get_ishotpatchable |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isHotpatchable method
ms.assetid: b7b6f490-1cf2-4a68-9237-b152dac84d3c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6ac1547228be6312126bb48602e3a77fed0b3c25
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63399929"
---
# <a name="idiasymbolgetishotpatchable"></a>IDiaSymbol::get_isHotpatchable
モジュールをコンパイルしたかどうかを示すフラグを取得、 [/hotpatch (ホットパッチ可能なイメージの作成)](/cpp/build/reference/hotpatch-create-hotpatchable-image)コンパイラ スイッチ。

## <a name="syntax"></a>構文

```C++
HRESULT get_isHotpatchable(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>パラメーター
 `pFlag`

[out]返します`TRUE`モジュールがホット パッチ可能なそれ以外の場合は、返す`FALSE`します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。

## <a name="remarks"></a>Remarks
 このプロパティは、`SymTagCompilandDetails`記号の型 (を参照してください[CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md))。

## <a name="requirements"></a>必要条件

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|Dia2.h|
|バージョン:|DIA SDK バージョン 8.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)