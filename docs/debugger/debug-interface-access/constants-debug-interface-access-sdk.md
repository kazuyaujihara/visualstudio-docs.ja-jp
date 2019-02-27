---
title: 定数 (Debug Interface Access SDK) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constants, DIA SDK
- DIA SDK, constants
ms.assetid: aca4ec77-bc08-4cdd-a6ce-8d4a28ea5ea3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ed505499efcabd7173fea9d668cd9afa5ed6d925
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56608579"
---
# <a name="constants-debug-interface-access-sdk"></a>定数 (Debug Interface Access SDK)
これらの文字列定数、DIA SDK を通じてプログラム デバッグ データベース (PDB) ファイルのさまざまなセクションを識別するために使用できます。

## <a name="constants"></a>定数
次は、C と C++ マクロとして宣言されます。

|マクロ|[値]|
|-----------|-----------|
|`DiaTable_Symbols`|L「シンボル」|
|`DiaTable_Sections`|L「セクション」|
|`DiaTable_SrcFiles`|L"SourceFiles"|
|`DiaTable_LineNums`|L"LineNumbers"|
|`DiaTable_SegMap`|L"SegmentMap"|
|`DiaTable_Dbg`|L"Dbg"|
|`DiaTable_InjSrc`|L"InjectedSource"|
|`DiaTable_FrameData`|L"FrameData"|

## <a name="example"></a>例
これらの記号のいずれかの使用例を次に示します。

```C++
HRESULT GetSymbolTable(IDiaEnumTables *pEnumTables, IDiaTable **pTable)
{
    HRESULT hr;
    VARIANT var;
    var.vt      = VT_BSTR;
    var.bstrVal = SysAllocString( DiaTable_Symbols );
    hr = pEnumTables->Item( var, pTable );
    return(hr);
}
```

## <a name="requirements"></a>要件
ヘッダー: dia2.h

## <a name="see-also"></a>参照
- [参照](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)
- [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)
