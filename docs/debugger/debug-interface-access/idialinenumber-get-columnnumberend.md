---
title: 'IDiaLineNumber:: get_columnNumberEnd |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_columnNumberEnd method
ms.assetid: 02fa56c1-87b6-405a-adee-3bb6bc62de2d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4433bc243a7a4f5352f0476370853572be8ddd38
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743245"
---
# <a name="idialinenumberget_columnnumberend"></a>IDiaLineNumber::get_columnNumberEnd
式またはステートメントの終了位置を示す、1から始まるソース列番号を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_columnNumberEnd ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力式またはステートメントの終了位置を示す列番号を返します。 値が0の場合、列の終了情報は存在しません。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドによって返される列の値は、行のステートメントの最後の文字の後の位置までのバイトオフセットです。

## <a name="see-also"></a>関連項目
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)