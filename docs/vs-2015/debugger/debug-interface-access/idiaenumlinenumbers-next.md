---
title: Idiaenumlinenumbers::next |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Next method
ms.assetid: 363d5b40-1316-4ab8-836f-63637f619e0a
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ebf4016b3bff52a74607fe01918655c0587f51d9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68190101"
---
# <a name="idiaenumlinenumbersnext"></a>IDiaEnumLineNumbers::Next
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

指定された数の列挙体シーケンス内の行番号を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT Next (   
   ULONG            celt,  
   IDiaLineNumber** rgelt,  
   ULONG*           pceltFetched  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 celt  
 [in]行番号を取得する列挙子の数。  
  
 rgelt  
 [out]配列を返します[IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)目的の行番号を表すオブジェクト。  
  
 pceltFetched  
 [out]フェッチされた列挙子の行番号の数を返します。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`ない複数の行番号がある場合。 それ以外の場合はエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)   
 [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)
