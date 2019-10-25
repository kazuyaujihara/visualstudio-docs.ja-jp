---
title: CustomType |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CustomType symbol
ms.assetid: 1b66bc0a-7979-416f-bf7f-e5df91584c91
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: be5ed68ef6923bfc58ebc072f27268e8d4e163b2
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745375"
---
# <a name="customtype"></a>CustomType
ベンダー定義型 (コンパイラ固有の型) は、`SymTagCustomType` シンボルによって識別されます。

## <a name="properties"></a>プロパティ
 次の表は、このシンボルの種類の追加の有効なプロパティを示しています。

|property|データの種類|説明|
|--------------|---------------|-----------------|
|[IDiaSymbol::get_oemId](../../debugger/debug-interface-access/idiasymbol-get-oemid.md)|`DWORD`|OEM の識別子。|
|[IDiaSymbol::get_oemSymbolId](../../debugger/debug-interface-access/idiasymbol-get-oemsymbolid.md)|`DWORD`|OEM の内部 ID。|
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|シンボルのインデックス ID。|
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|@No__t_0 ( [Symtagenum 列挙](../../debugger/debug-interface-access/symtagenum.md)値のいずれか) を返します。|
|[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|カスタム型シンボルによって参照される最初の型。|
|[IDiaSymbol::get_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|型シンボルの ID。|
|[IDiaSymbol::get_types](../../debugger/debug-interface-access/idiasymbol-get-types.md)|`IDiaSymbol**`|カスタム型シンボルによって参照されるすべての型の配列。|

## <a name="see-also"></a>関連項目
- [シンボル型のクラス階層](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)