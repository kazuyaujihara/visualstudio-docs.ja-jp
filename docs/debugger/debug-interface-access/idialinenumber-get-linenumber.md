---
title: 'IDiaLineNumber:: get_lineNumber |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_lineNumber method
ms.assetid: 2dff3fd9-097d-4645-bc1b-cb65ecbc42a6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 726f5df7ff898675fc9253b47785c666d435a387
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743206"
---
# <a name="idialinenumberget_linenumber"></a>IDiaLineNumber::get_lineNumber
ソースファイル内の行番号を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_lineNumber ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力ソースファイル内の行番号を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="example"></a>例

```C++
CComPtr< IDiaLineNumber> pLine;
DWORD linenum;
pLine->get_lineNumber( &linenum );
```

## <a name="see-also"></a>関連項目
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)