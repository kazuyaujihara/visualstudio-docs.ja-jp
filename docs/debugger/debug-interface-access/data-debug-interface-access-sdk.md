---
title: データ (Debug Interface Access SDK) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- global variables [C++], as symbols
- local variables [C++], as symbols
- class members [C++], as symbols
- Data symbol
ms.assetid: 0f17e96a-2e06-42c9-a877-3e5e670ee0ef
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 94e1be7a1809c52683be045f71fcc681a6b270a8
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745297"
---
# <a name="data-debug-interface-access-sdk"></a>データ (Debug Interface Access SDK)
パラメーター、ローカル変数、グローバル変数、クラスメンバーなど、すべての変数は `SymTagData` シンボルによって識別されます。 定数値 (`LocIsConstant`) もこの型で識別されます。

## <a name="properties"></a>プロパティ
 次の表は、このシンボルの種類に対して有効なプロパティを示しています。

|property|データの種類|説明|
|--------------|---------------|-----------------|
|[IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|フィールドの場合は、 [CV_access_e 列挙](../../debugger/debug-interface-access/cv-access-e.md)値のいずれかです。|
|[IDiaSymbol::get_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|位置のオフセット部分です。詳細については、 [LocationType 列挙体](../../debugger/debug-interface-access/locationtype.md)を参照してください。|
|[IDiaSymbol::get_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|セクションの位置の部分。詳細については、 [LocationType 列挙体](../../debugger/debug-interface-access/locationtype.md)を参照してください。|
|[IDiaSymbol::get_addressTaken](../../debugger/debug-interface-access/idiasymbol-get-addresstaken.md)|`BOOL`|このデータのアドレスが別のシンボルによって参照されている場合は `TRUE` します。|
|[IDiaSymbol::get_bitPosition](../../debugger/debug-interface-access/idiasymbol-get-bitposition.md)|`DWORD`|位置のビット位置。詳細については、「 [LocationType 列挙型](../../debugger/debug-interface-access/locationtype.md)(DIA SDK v2.0 ではサポートされていません)」を参照してください。|
|[IDiaSymbol::get_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|構造体、共用体、またはクラスフィールドの場合は、クラスのシンボル。|
|[IDiaSymbol::get_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|クラスの親シンボルの ID。|
|[IDiaSymbol::get_compilerGenerated](../../debugger/debug-interface-access/idiasymbol-get-compilergenerated.md)|`BOOL`|データがコンパイラによって生成されたかどうかを `TRUE` します。|
|[IDiaSymbol::get_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|データが定数としてマークされているかどうかを `TRUE` します。|
|[IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)|`DWORD`|[Datakind 列挙](../../debugger/debug-interface-access/datakind.md)値のいずれか。|
|[IDiaSymbol::get_isAggregated](../../debugger/debug-interface-access/idiasymbol-get-isaggregated.md)|`BOOL`|データが集計データ型の一部である場合は `TRUE` します (DIA SDK v2.0 以降のみ)。|
|[IDiaSymbol::get_isSplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)|`BOOL`|データが複数のシンボルの集計に分割されている場合は `TRUE` します (DIA SDK v2.0 以降でのみ)。|
|[IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|ビットフィールドの長さ。詳細については、 [LocationType 列挙体](../../debugger/debug-interface-access/locationtype.md)を参照してください。|
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|外側のコンパイル単位、function、または block のシンボル。|
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|構文の親シンボルの ID。|
|[IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|許容される任意の場所の種類。詳細については、「[シンボルの場所](../../debugger/debug-interface-access/symbol-locations.md)」を参照してください|
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|変数名。|
|[IDiaSymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|レジスタの内容からのオフセット。詳細については、 [LocationType 列挙体](../../debugger/debug-interface-access/locationtype.md)を参照してください。|
|[IDiaSymbol::get_registerId](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)|`DWORD`|場所の指定子を登録します。詳細については、 [LocationType 列挙体](../../debugger/debug-interface-access/locationtype.md)を参照してください。|
|[IDiaSymbol::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|ブロック内のデータの相対位置。|
|[IDiaSymbol::get_slot](../../debugger/debug-interface-access/idiasymbol-get-slot.md)|`DWORD`|データのスロット番号を取得します。|
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|シンボルのインデックス ID。|
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|@No__t_0 ( [Symtagenum 列挙](../../debugger/debug-interface-access/symtagenum.md)値のいずれか) を返します。|
|[IDiaSymbol::get_token](../../debugger/debug-interface-access/idiasymbol-get-token.md)|`DWORD`|データを表すメタデータトークン。|
|[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|変数の型のシンボル。|
|[IDiaSymbol::get_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|変数の型シンボルの ID。|
|[IDiaSymbol::get_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|データが整列されていない場合は `TRUE` します。|
|[IDiaSymbol::get_value](../../debugger/debug-interface-access/idiasymbol-get-value.md)|`VARIANT`|定数データの値。|
|[IDiaSymbol::get_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|実行可能ファイル内のデータの位置。|
|[IDiaSymbol::get_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|データが揮発性としてマークされている場合は `TRUE` します。|

## <a name="see-also"></a>関連項目
- [CV_access_e 列挙型](../../debugger/debug-interface-access/cv-access-e.md)
- [DataKind 列挙型](../../debugger/debug-interface-access/datakind.md)
- [シンボル型の構文階層](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)
- [LocationType 列挙型](../../debugger/debug-interface-access/locationtype.md)
- [シンボルの場所](../../debugger/debug-interface-access/symbol-locations.md)