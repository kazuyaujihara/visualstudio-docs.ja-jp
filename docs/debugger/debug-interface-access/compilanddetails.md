---
title: CompilandDetails |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CompilandDetails symbol
ms.assetid: ddc7d794-c622-4c63-b2a6-72f8b2d0022a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b72a5ae53c336877c68cc9b164cf787017dacbe2
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745415"
---
# <a name="compilanddetails"></a>CompilandDetails
コンパイル単位の情報は、`SymTagCompiland` タグ (低詳細) と `SymTagCompilandDetails` タグ (詳細) を含むシンボル間で分割されます。 `SymTagCompilandDetails` には、追加のシンボルを読み込む必要があります。 ただし、`SymTagCompiland` シンボルでは使用できないコンパイル単位に関する豊富な情報を提供します。

## <a name="properties"></a>プロパティ
 次の表は、このシンボルの種類に対して有効なプロパティを示しています。

|property|データの種類|説明|
|--------------|---------------|-----------------|
|[IDiaSymbol::get_backEndBuild](../../debugger/debug-interface-access/idiasymbol-get-backendbuild.md)|`DWORD`|コンパイラのバックエンドビルド番号。|
|[IDiaSymbol::get_backEndMajor](../../debugger/debug-interface-access/idiasymbol-get-backendmajor.md)|`DWORD`|コンパイラのバックエンドメジャーバージョン番号。|
|[IDiaSymbol::get_backEndMinor](../../debugger/debug-interface-access/idiasymbol-get-backendminor.md)|`DWORD`|コンパイラのバックエンドマイナーバージョン番号。|
|[IDiaSymbol::get_compilerName](../../debugger/debug-interface-access/idiasymbol-get-compilername.md)|`BSTR`|このコンパイル単位を生成したコンパイラの名前 (DIA SDK v2.0 以降でのみ)。|
|[IDiaSymbol::get_editAndContinueEnabled](../../debugger/debug-interface-access/idiasymbol-get-editandcontinueenabled.md)|`BOOL`|コンパイル時にエディットコンティニュが有効にされた場合は `TRUE` します。|
|[IDiaSymbol::get_frontEndBuild](../../debugger/debug-interface-access/idiasymbol-get-frontendbuild.md)|`DWORD`|コンパイラのフロントエンドビルド番号。|
|[IDiaSymbol::get_frontEndMajor](../../debugger/debug-interface-access/idiasymbol-get-frontendmajor.md)|`DWORD`|コンパイラのフロントエンドメジャーバージョン番号。|
|[IDiaSymbol::get_frontEndMinor](../../debugger/debug-interface-access/idiasymbol-get-frontendminor.md)|`DWORD`|コンパイラのフロントエンドマイナーバージョン番号。|
|[IDiaSymbol::get_hasDebugInfo](../../debugger/debug-interface-access/idiasymbol-get-hasdebuginfo.md)|`BOOL`|このコンパイル単位にデバッグ情報がある場合は `TRUE` します (DIA SDK v2.0 以降のみ)。|
|[IDiaSymbol::get_hasManagedCode](../../debugger/debug-interface-access/idiasymbol-get-hasmanagedcode.md)|`BOOL`|このコンパイル単位にマネージコードが含まれている場合は `TRUE` します (DIA SDK v2.0 以降のみ)。|
|[IDiaSymbol::get_hasSecurityChecks](../../debugger/debug-interface-access/idiasymbol-get-hassecuritychecks.md)|`BOOL`|コンパイル単位が[/gs (バッファーセキュリティチェック)](/cpp/build/reference/gs-buffer-security-check)コンパイラスイッチ (DIA SDK v2.0 以降でのみ) でコンパイルされた場合に `TRUE` します。|
|[IDiaSymbol::get_isCVTCIL](../../debugger/debug-interface-access/idiasymbol-get-iscvtcil.md)|`BOOL`|コンパイル単位が共通中間言語 (CIL) コードからネイティブコードに変換されたかどうかを `TRUE` します。|
|[IDiaSymbol::get_isDataAligned](../../debugger/debug-interface-access/idiasymbol-get-isdataaligned.md)|`BOOL`|ユーザー定義型 (UDT) が指定したメモリ境界に固定されている場合は `TRUE` します (DIA SDK v2.0 以降でのみ)。|
|[IDiaSymbol::get_isHotpatchable](../../debugger/debug-interface-access/idiasymbol-get-ishotpatchable.md)|`BOOL`|コンパイル単位が[/hotpatch (Hotpatchable イメージの作成)](/cpp/build/reference/hotpatch-create-hotpatchable-image)コンパイラスイッチを使用してコンパイルされた場合に `TRUE` ます (DIA SDK v2.0 以降でのみ)。|
|[IDiaSymbol::get_isLTCG](../../debugger/debug-interface-access/idiasymbol-get-isltcg.md)|`BOOL`|コンパイル単位が[/ltcg (リンク時のコード生成)](/cpp/build/reference/ltcg-link-time-code-generation)コンパイラスイッチを使用してコンパイルされた場合に `TRUE` ます (DIA SDK v2.0 以降でのみ)。|
|[IDiaSymbol::get_isMSILNetmodule](../../debugger/debug-interface-access/idiasymbol-get-ismsilnetmodule.md)|`BOOL`|コンパイル単位が Microsoft 中間言語 (MSIL) モジュールの場合は TRUE、(DIA SDK v2.0 以降でのみ)。|
|[IDiaSymbol::get_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)|`DWORD`|ソース コード言語。|
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|コンパイル単位のシンボル。|
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|構文の親シンボルの ID。|
|[IDiaSymbol::get_platform](../../debugger/debug-interface-access/idiasymbol-get-platform.md)|`DWORD`|コンパイル単位がコンパイルされたプラットフォーム ( [CV_CPU_TYPE_e 列挙](../../debugger/debug-interface-access/cv-cpu-type-e.md)値のいずれか)。|
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|シンボルのインデックス ID。|
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|@No__t_0 ( [Symtagenum 列挙](../../debugger/debug-interface-access/symtagenum.md)値のいずれか) を返します。|

## <a name="remarks"></a>Remarks
 多くの場合、コンパイラは2パスコンパイラと呼ばれる形式です。コンパイラのバージョンによっては、各パスが個別のプログラムによって処理される場合があります。 これらはそれぞれフロントエンドとバックエンドのコンパイラと呼ばれます。そのため、バックエンドとフロントエンドのバージョン番号のシンボルプロパティを使用します。

## <a name="see-also"></a>関連項目
- [コンパイル単位](../../debugger/debug-interface-access/compiland.md)
- [シンボル型の構文階層](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)