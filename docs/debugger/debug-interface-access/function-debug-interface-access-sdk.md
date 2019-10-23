---
title: 関数 (Debug Interface Access SDK) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Function symbol
ms.assetid: 458dc91c-b78b-4427-84f4-615d89e26760
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bd901d1bb54f91042e0a8134f1f3cba6c29b396a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745127"
---
# <a name="function-debug-interface-access-sdk"></a>関数 (Debug Interface Access SDK)
各関数は、`SymTagFunction` シンボルによって識別されます。

## <a name="properties"></a>プロパティ
 次の表は、このシンボルの種類に対して有効なプロパティを示しています。

|property|`Data type`|説明|
|--------------|-----------------|-----------------|
|[IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|関数がメンバー関数の場合は、 [CV_access_e 列挙体](../../debugger/debug-interface-access/cv-access-e.md)の値の1つ。|
|[IDiaSymbol::get_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|位置のオフセット部分です。詳細については、 [LocationType 列挙体](../../debugger/debug-interface-access/locationtype.md)を参照してください。|
|[IDiaSymbol::get_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|セクションの位置の部分。詳細については、 [LocationType 列挙体](../../debugger/debug-interface-access/locationtype.md)を参照してください。|
|[IDiaSymbol::get_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|関数がメンバー関数の場合は、クラスのシンボル。|
|[IDiaSymbol::get_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|クラスの親シンボルの ID。|
|[IDiaSymbol::get_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|関数が定数としてマークされているかどうかを `TRUE` します。|
|[IDiaSymbol::get_customCallingConvention](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|`BOOL`|関数がカスタム呼び出し規約を使用するかどうかを `TRUE` します (DIA SDK v2.0 以降でのみ)。|
|[IDiaSymbol::get_farReturn](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|`BOOL`|関数が far を返す (DIA SDK v2.0 以降でのみ) かどうかを `TRUE` します。|
|[IDiaSymbol::get_hasAlloca](../../debugger/debug-interface-access/idiasymbol-get-hasalloca.md)|`BOOL`|関数が割り当てられたメモリ関数を使用するかどうかを `TRUE` します (uinnder DIA SDK v2.0 以降のみ)。|
|[IDiaSymbol::get_hasEH](../../debugger/debug-interface-access/idiasymbol-get-haseh.md)|`BOOL`|関数にスタイルの例外C++処理が含まれている場合は `TRUE` します (DIA SDK v2.0 以降の場合のみ)。|
|[IDiaSymbol::get_hasEHa](../../debugger/debug-interface-access/idiasymbol-get-haseha.md)|`BOOL`|関数に非同期例外処理 (DIA SDK v2.0 以降でのみ) が含まれている場合は `TRUE` します。|
|[IDiaSymbol::get_hasInlAsm](../../debugger/debug-interface-access/idiasymbol-get-hasinlasm.md)|`BOOL`|関数にインラインアセンブリが含まれている場合は `TRUE` します (DIA SDK v2.0 以降でのみ)。|
|[IDiaSymbol::get_hasLongJump](../../debugger/debug-interface-access/idiasymbol-get-haslongjump.md)|`BOOL`|関数に[longjmp](/cpp/c-runtime-library/reference/longjmp)呼び出しが含まれている場合は `TRUE` します (DIA SDK v2.0 以降でのみ)。|
|[IDiaSymbol::get_hasSecurityChecks](../../debugger/debug-interface-access/idiasymbol-get-hassecuritychecks.md)|`BOOL`|関数にセキュリティチェックが含まれている場合は `TRUE` します (DIA SDK v2.0 以降のみ)。|
|[IDiaSymbol::get_hasSEH](../../debugger/debug-interface-access/idiasymbol-get-hasseh.md)|`BOOL`|関数に Win32 スタイルの構造化例外処理が含まれているかどうかを `TRUE` します (DIA SDK v2.0 以降のみ)。|
|[IDiaSymbol::get_hasSetJump](../../debugger/debug-interface-access/idiasymbol-get-hassetjump.md)|`BOOL`|関数に[setjmp](/cpp/c-runtime-library/reference/setjmp)呼び出しが含まれている場合は `TRUE` します (DIA SDK v2.0 以降でのみ)。|
|[IDiaSymbol::get_interruptReturn](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|`BOOL`|関数に割り込みからの戻り値がある場合は `TRUE` します (DIA SDK v2.0 以降でのみ)。|
|[IDiaSymbol::get_intro](../../debugger/debug-interface-access/idiasymbol-get-intro.md)|`BOOL`|関数が仮想の導入であるかどうかを `TRUE` します。|
|[IDiaSymbol::get_InlSpec](../../debugger/debug-interface-access/idiasymbol-get-inlspec.md)|`BOOL`|関数が[inline、__ inline、\__forceinline](/cpp/cpp/inline-functions-cpp)のいずれかの属性でマークされているかどうかを `TRUE` します。|
|[IDiaSymbol::get_isNaked](../../debugger/debug-interface-access/idiasymbol-get-isnaked.md)|`BOOL`|関数が[生](/cpp/cpp/naked-cpp)の属性でマークされている場合は `TRUE` ます (DIA SDK v2.0 以降でのみ)。|
|[IDiaSymbol::get_isStatic](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|関数が静的 (DIA SDK v2.0 以降でのみ) の場合は `TRUE`。|
|[IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|位置から始まる関数コードのバイト数。|
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|外側のコンパイル単位のシンボル。|
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|構文の親シンボルの ID。|
|[IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|関数には、静的またはメタデータの場所を含めることができます。詳細については、「[シンボルの場所](../../debugger/debug-interface-access/symbol-locations.md)」を参照してください。|
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|関数名。|
|[IDiaSymbol::get_noInline](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|`BOOL`|関数がインライン関数でない場合は `TRUE` します (n DIA SDK Version 8.0 以降のみ)。|
|[IDiaSymbol::get_notReached](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|`BOOL`|関数に到達できない場合は `TRUE` します (DIA SDK v2.0 以降でのみ)。|
|[IDiaSymbol::get_noReturn](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|`BOOL`|関数が値を返さない場合 (DIA SDK v2.0 以降でのみ) `TRUE`。|
|[IDiaSymbol::get_noStackOrdering](../../debugger/debug-interface-access/idiasymbol-get-nostackordering.md)|`BOOL`|関数がバッファーセキュリティチェックを使用してコンパイルされたが、スタックの順序付けができなかった場合に `TRUE` します。|
|[IDiaSymbol::get_optimizedCodeDebugInfo](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|`BOOL`|コードに最適化されたコードのデバッグ情報があるかどうかを `TRUE` します (DIA SDK v2.0 以降のみ)。|
|[IDiaSymbol::get_pure](../../debugger/debug-interface-access/idiasymbol-get-pure.md)|`BOOL`|関数が純粋仮想の場合は `TRUE`。|
|[IDiaSymbol::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|モジュール内でのこの関数の相対位置。|
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|シンボルのインデックス ID。|
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|@No__t_0 ( [Symtagenum 列挙](../../debugger/debug-interface-access/symtagenum.md)値のいずれか) を返します。|
|[IDiaSymbol::get_token](../../debugger/debug-interface-access/idiasymbol-get-token.md)|`DWORD`|関数のメタデータトークン。|
|[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|関数シグネチャのシンボル。|
|[IDiaSymbol::get_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|型シンボルの ID。|
|[IDiaSymbol::get_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|関数が整列されていない場合は `TRUE` します。|
|[IDiaSymbol::get_undecoratedName](../../debugger/debug-interface-access/idiasymbol-get-undecoratedname.md)|`BSTR`|関数名の非装飾形式 (DIA SDK v2.0 以降のみ)|
|[IDiaSymbol::get_undecoratedNameEx](../../debugger/debug-interface-access/idiasymbol-get-undecoratednameex.md)|`BSTR`|関数名の装飾されていない形式の一部またはすべて (DIA SDK v2.0 以降のみ)。|
|[IDiaSymbol::get_virtual](../../debugger/debug-interface-access/idiasymbol-get-virtual.md)|`BOOL`|仮想関数の場合は `TRUE`。|
|[IDiaSymbol::get_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|実行可能イメージ内でのこの関数の位置。|
|[IDiaSymbol::get_virtualBaseOffset](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseoffset.md)|`DWORD`|仮想関数の場合は、仮想関数テーブル内のオフセット。|
|[IDiaSymbol::get_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|関数が volatile としてマークされているかどうかを `TRUE` します。|

## <a name="see-also"></a>関連項目
- [CV_access_e 列挙型](../../debugger/debug-interface-access/cv-access-e.md)
- [シンボル型の構文階層](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)
- [LocationType 列挙型](../../debugger/debug-interface-access/locationtype.md)
- [シンボルの場所](../../debugger/debug-interface-access/symbol-locations.md)