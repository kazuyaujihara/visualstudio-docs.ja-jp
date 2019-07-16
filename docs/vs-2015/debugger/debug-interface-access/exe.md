---
title: Exe |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- .dll files
- Exe symbol
- .exe files
- executable files, Exe symbol
ms.assetid: a781d2cf-55fe-4373-9cf1-b732864244e0
caps.latest.revision: 20
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: fe2930e0947bf0fa69408dc81c19d058d6cdd870
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68164263"
---
# <a name="exe"></a>Exe
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Exe は、.exe または .dll ファイルのグローバル スコープを表しているために、唯一のことがなく、構文のシンボルまたは親のクラスします。 1 つだけのシンボルがある、`SymTagExe`ファイルあたりのタグ。 [Idiasession::get_globalscope](../../debugger/debug-interface-access/idiasession-get-globalscope.md)メソッドは、シンボルを返します。  
  
## <a name="properties"></a>Properties  
 次の表では、この記号の型の有効なプロパティを示します。  
  
|プロパティ|データの種類|説明|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_age](../../debugger/debug-interface-access/idiasymbol-get-age.md)|`DWORD`|この実行可能ファイルの経過時間。|  
|[IDiaSymbol::get_guid](../../debugger/debug-interface-access/idiasymbol-get-guid.md)|`GUID`|`GUID` この実行可能ファイルです。|  
|[IDiaSymbol::get_isCTypes](../../debugger/debug-interface-access/idiasymbol-get-isctypes.md)|`BOOL`|`TRUE` シンボル ファイルに関連付けられている場合、この実行可能ファイルには、C の型 (DIA SDK バージョン 8.0 でのみまたはそれ以降) が含まれています。|  
|[IDiaSymbol::get_isStripped](../../debugger/debug-interface-access/idiasymbol-get-isstripped.md)|`BOOL`|`TRUE` 場合はプライベート シンボルが (DIA SDK バージョン 8.0 でのみまたはそれ以降) この実行可能ファイルに関連付けられているシンボル ファイルから削除されました。|  
|[IDiaSymbol::get_machineType](../../debugger/debug-interface-access/idiasymbol-get-machinetype.md)|`DWORD`|ターゲット CPU を示す値 (1 つの[CV_CPU_TYPE_e 列挙型](../../debugger/debug-interface-access/cv-cpu-type-e.md)値)。|  
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|.Exe ファイルの名前。|  
|[IDiaSymbol::get_signature](../../debugger/debug-interface-access/idiasymbol-get-signature.md)|`DWORD`|実行可能ファイルの署名。|  
|[IDiaSymbol::get_symbolsFileName](../../debugger/debug-interface-access/idiasymbol-get-symbolsfilename.md)|`BSTR`|.Exe ファイルの .pdb ファイルまたは .dbg ファイルの完全パス。|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|シンボルのインデックス ID。|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|返します`SymTagExe`(の 1 つ、 [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)値)。|  
  
## <a name="see-also"></a>関連項目  
 [IDiaSession::get_globalScope](../../debugger/debug-interface-access/idiasession-get-globalscope.md)   
 [シンボル型の構文階層](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)
