---
title: コンパイル単位 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- compiland symbol
- compilands, compiland symbol
ms.assetid: c798eb2b-664a-41ec-ae90-5e9d292507ca
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ccb4ca05374c86912cd48956262645b80fb14e40
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745440"
---
# <a name="compiland"></a>コンパイル単位
.Exe ファイルにリンクされているコンパイル単位ごとに1つの `SymTagCompiland` シンボルがあります。 コンパイル単位情報は `SymTagCompiland` タグを持つシンボル間で分割されます。これは追加のコンパイル単位シンボルを読み込まずに取得できます。また、`SymTagCompilandDetails` タグを持つシンボルは、追加のシンボルを読み込む必要がある場合があります。

## <a name="properties"></a>プロパティ
 次の表は、このシンボルの種類に対して有効なプロパティを示しています。

|property|データの種類|説明|
|--------------|---------------|-----------------|
|[IDiaSymbol::get_editAndContinueEnabled](../../debugger/debug-interface-access/idiasymbol-get-editandcontinueenabled.md)|`BOOL`|コンパイル時にエディットコンティニュが有効になった場合は `TRUE` します。|
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|.Exe ファイルのシンボル。|
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|構文の親シンボルの ID。|
|[IDiaSymbol::get_libraryName](../../debugger/debug-interface-access/idiasymbol-get-libraryname.md)|`BSTR`|オブジェクトが読み込まれたライブラリまたはオブジェクトファイルの名前。|
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|コンパイル単位のオブジェクトファイルのファイル名。|
|[IDiaSymbol::get_sourceFileName](../../debugger/debug-interface-access/idiasymbol-get-sourcefilename.md)|`BSTR`|ソースファイルの名前。|
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|シンボルのインデックス ID。|
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|@No__t_0 ( [Symtagenum 列挙](../../debugger/debug-interface-access/symtagenum.md)値のいずれか) を返します。|

## <a name="see-also"></a>関連項目
- [CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)
- [CompilandEnv](../../debugger/debug-interface-access/compilandenv.md)
- [シンボル型の構文階層](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)