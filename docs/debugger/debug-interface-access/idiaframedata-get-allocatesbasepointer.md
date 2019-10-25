---
title: 'IDiaFrameData:: get_allocatesBasePointer |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_allocatesBasePointer method
ms.assetid: 8a33db5d-008c-4fe5-b64f-210c9b77f686
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 283ef71b32c186956804cb3afe121af53a99abfc
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743653"
---
# <a name="idiaframedataget_allocatesbasepointer"></a>IDiaFrameData::get_allocatesBasePointer
このアドレス範囲内のコードに対してベースポインターが割り当てられているかどうかを示すフラグを取得します。 このメソッドは非推奨です。

## <a name="syntax"></a>構文

```C++
HRESULT get_allocatesBasePointer ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力ベースポインターが割り当てられている場合は `TRUE` を返します。それ以外の場合は `FALSE` を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 このプロパティは、以前に FPO_DATA にアクセスしたコード、または[IDiaFrameData:: get_program](../../debugger/debug-interface-access/idiaframedata-get-program.md)メソッドによって返されたプログラム文字列が `NULL` 場合にのみ使用してください。 それ以外の場合、プログラム文字列には、以前のレジスタ値を計算するために必要なすべての情報が含まれます。

## <a name="see-also"></a>関連項目
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
- [IDiaFrameData::get_program](../../debugger/debug-interface-access/idiaframedata-get-program.md)