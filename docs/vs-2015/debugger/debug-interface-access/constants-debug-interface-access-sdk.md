---
title: 定数 (Debug Interface Access SDK) |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- constants, DIA SDK
- DIA SDK, constants
ms.assetid: aca4ec77-bc08-4cdd-a6ce-8d4a28ea5ea3
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 931e1ab46793a5ff7e0434949330eaf4dbc820e8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68164426"
---
# <a name="constants-debug-interface-access-sdk"></a>定数 (Debug Interface Access SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

これらの文字列定数、DIA SDK を通じてプログラム デバッグ データベース (PDB) ファイルのさまざまなセクションを識別するために使用できます。  
  
## <a name="constants"></a>定数  
 次は、C と C++ マクロとして宣言されます。  
  
|マクロ|値|  
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
  
```cpp#  
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
  
## <a name="requirements"></a>必要条件  
 ヘッダー: dia2.h  
  
## <a name="see-also"></a>関連項目  
 [リファレンス](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)   
 [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)
