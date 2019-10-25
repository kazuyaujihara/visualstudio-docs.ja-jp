---
title: BaseClass |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user-defined types, base classes
- BaseClass symbol
- base classes, user-defined types
ms.assetid: 9375ca35-cb91-45f5-8903-7344ee4528e8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a98a6b053234089ecf7e340bab1dd214e3908662
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745488"
---
# <a name="baseclass"></a>BaseClass
ユーザー定義型 (UDT) シンボルの各基底クラスは、`SymTagBaseClass` タグを持つ子によって識別されます。 [IDiaSymbol:: get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)プロパティには、基になる udt のシンボルが含まれます。基になる udt のすべてのプロパティは、この BaseClass シンボルの一部として使用できます。

## <a name="properties"></a>プロパティ
 次の表は、このシンボルの種類の追加の有効なプロパティを示しています。

|property|データの種類|説明|
|--------------|---------------|-----------------|
|[IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|この基底クラスに適用されるアクセス修飾子。 [CV_access_e 列挙](../../debugger/debug-interface-access/cv-access-e.md)値のいずれか。|
|[IDiaSymbol::get_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|外側のクラスのシンボル (存在する場合)。|
|[IDiaSymbol::get_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|クラスの親シンボルの ID。|
|[IDiaSymbol::get_constructor](../../debugger/debug-interface-access/idiasymbol-get-constructor.md)|`BOOL`|基底クラスにコンストラクターがある場合は `TRUE` します。|
|[IDiaSymbol::get_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|基底クラスが const としてマークされている場合に `TRUE` します。|
|[IDiaSymbol::get_hasAssignmentOperator](../../debugger/debug-interface-access/idiasymbol-get-hasassignmentoperator.md)|`BOOL`|基底クラスに代入演算子がある場合は `TRUE` します。|
|[IDiaSymbol::get_hasCastOperator](../../debugger/debug-interface-access/idiasymbol-get-hascastoperator.md)|`BOOL`|基底クラスに cast 演算子がある場合に `TRUE` します。|
|[IDiaSymbol::get_hasNestedTypes](../../debugger/debug-interface-access/idiasymbol-get-hasnestedtypes.md)|`BOOL`|基底クラスに入れ子にされた型がある場合は `TRUE` します。|
|[IDiaSymbol::get_indirectVirtualBaseClass](../../debugger/debug-interface-access/idiasymbol-get-indirectvirtualbaseclass.md)|`BOOL`|基底クラスが間接的である場合は `TRUE` します。|
|[IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`DWORD`|この基底クラスの長さ (バイト単位)。|
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|外側のコンパイル単位のシンボル。|
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|構文の親シンボルの ID。|
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|基底クラスの名前。|
|[IDiaSymbol::get_nested](../../debugger/debug-interface-access/idiasymbol-get-nested.md)|`BOOL`|基底クラスが入れ子になっている場合は `TRUE` します。|
|[IDiaSymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|構造体内の基底クラスを表すサブオブジェクトのオフセット。|
|[IDiaSymbol::get_overloadedOperator](../../debugger/debug-interface-access/idiasymbol-get-overloadedoperator.md)|`BOOL`|基底クラスにオーバーロードされた演算子があるかどうかを `TRUE` します。|
|[IDiaSymbol::get_packed](../../debugger/debug-interface-access/idiasymbol-get-packed.md)|`BOOL`|基本クラスがパックされている場合は `TRUE` します。|
|[IDiaSymbol::get_scoped](../../debugger/debug-interface-access/idiasymbol-get-scoped.md)|`BOOL`|基底クラスが非グローバルスコープに表示される場合は `TRUE` します。|
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|シンボルのインデックス ID。|
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|@No__t_0 ( [Symtagenum 列挙](../../debugger/debug-interface-access/symtagenum.md)値のいずれか) を返します。|
|[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|基底クラスの[UDT](../../debugger/debug-interface-access/udt.md)のシンボル。|
|[IDiaSymbol::get_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|型シンボルの ID。|
|[IDiaSymbol::get_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)|`DWORD`|[Udtkind 列挙子](../../debugger/debug-interface-access/udtkind.md)の値。|
|[IDiaSymbol::get_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|基底クラスが整列されていない場合は `TRUE` します。|
|[IDiaSymbol::get_virtualBaseClass](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseclass.md)|`BOOL`|基底クラスが virtual の場合に `TRUE` します。|
|[IDiaSymbol::get_virtualBaseDispIndex](../../debugger/debug-interface-access/idiasymbol-get-virtualbasedispindex.md)|`DWORD`|仮想ベースのディスプレイスメントテーブルにインデックスを作成します。|
|[IDiaSymbol::get_virtualBasePointerOffset](../../debugger/debug-interface-access/idiasymbol-get-virtualbasepointeroffset.md)|`LONG`|仮想基本ポインターのオフセット。|
|[IDiaSymbol::get_virtualBaseTableType](../../debugger/debug-interface-access/idiasymbol-get-virtualbasetabletype.md)|`IDiaSymbol*`|仮想ベーステーブルポインターの型。|
|[IDiaSymbol::get_virtualTableShape](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshape.md)|`IDiaSymbol*`|この基本クラスの仮想テーブルの型を記述するシンボル。|
|[IDiaSymbol::get_virtualTableShapeId](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshapeid.md)|`DWORD`|仮想テーブル図形のシンボルの ID。|
|[IDiaSymbol::get_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|基底クラスが volatile としてマークされている場合に `TRUE` します。|

## <a name="see-also"></a>関連項目
- [シンボル型のクラス階層](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)
- [UDT](../../debugger/debug-interface-access/udt.md)