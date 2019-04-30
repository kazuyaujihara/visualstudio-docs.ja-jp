---
title: Idialinenumber::get_statement |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_statement method
ms.assetid: 22b8ee29-79ef-427f-bd05-00d255ab836b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 397873a65176024327f371e9727b15984cd7d03f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62828392"
---
# <a name="idialinenumbergetstatement"></a>IDiaLineNumber::get_statement
この行の情報がプログラムのソース内の式ではなく、ステートメントの先頭を説明することを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_statement ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]返します`TRUE`場合、この行の情報には、プログラムのソース内のステートメントの先頭がについて説明します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`場合、このプロパティはサポートされていません。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 ステートメントは、複数の行にまたがることができます。 このメソッドは、関連付けられている行番号が、このような複数行ステートメントの先頭をマークするかどうかを示します。

## <a name="see-also"></a>関連項目
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)