---
title: 'IDiaLineNumber:: get_statement |Microsoft Docs'
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
ms.openlocfilehash: 0a37052944f74e36b488541074a0033f5b8aca9e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743131"
---
# <a name="idialinenumberget_statement"></a>IDiaLineNumber::get_statement
この行情報で、プログラムソースの式ではなく、ステートメントの先頭が記述されていることを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_statement ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力この行情報でプログラムソースのステートメントの先頭が記述されている場合は、`TRUE` を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 ステートメントは複数の行にまたがることができます。 このメソッドは、関連付けられている行番号が、このような複数行ステートメントの先頭を示すかどうかを示します。

## <a name="see-also"></a>関連項目
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)