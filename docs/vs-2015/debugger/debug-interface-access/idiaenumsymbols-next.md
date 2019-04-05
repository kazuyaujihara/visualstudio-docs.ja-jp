---
title: Idiaenumsymbols::next |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbols::Next method
ms.assetid: bfe5fe27-6a84-4392-910f-e325146d7552
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cdea32ece50e83c046a67399a0d5f36410edb9a1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973955"
---
# <a name="idiaenumsymbolsnext"></a>IDiaEnumSymbols::Next
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

指定された数の列挙体シーケンス内のシンボルを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT Next (   
   ULONG        celt,  
   IDiaSymbol** rgelt,  
   ULONG*       pceltFetched  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 celt  
 [in]シンボルを取得する列挙子の数。  
  
 rgelt  
 [out]格納する配列、 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)必要なシンボルを表すオブジェクト。  
  
 pceltFetched  
 [out]フェッチされた列挙子の記号の数を返します。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`シンボルがある場合。 それ以外の場合はエラー コードを返します。  
  
## <a name="example"></a>例  
  
```cpp#  
IDiaEnumSymbols* pEnum  
CComPtr< IDiaSymbol> pSym;  
DWORD celt;  
pEnum->Next( 1, &pSym, &celt );  
```  
  
## <a name="see-also"></a>関連項目  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
