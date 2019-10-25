---
title: 'IDiaFrameData:: get_systemExceptionHandling |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_systemExceptionHandling method
ms.assetid: e8df1972-913c-446c-9779-775575b0caa9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9e73ed8ae4aacf739463b1c6ab1f8f30c51a7fb2
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743493"
---
# <a name="idiaframedataget_systemexceptionhandling"></a>IDiaFrameData::get_systemExceptionHandling
システム例外処理が有効かどうかを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_systemExceptionHandling ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 の場合は、

入出力システム例外処理が有効な場合は `TRUE` を返します。それ以外の場合は `FALSE` を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 システム例外処理は、構造化例外処理としてよく知られています。

 C++例外処理が有効かどうかを判断するには、 [IDiaFrameData:: get_cplusplusExceptionHandling](../../debugger/debug-interface-access/idiaframedata-get-cplusplusexceptionhandling.md)メソッドを呼び出します。

## <a name="see-also"></a>関連項目
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
- [IDiaFrameData::get_cplusplusExceptionHandling](../../debugger/debug-interface-access/idiaframedata-get-cplusplusexceptionhandling.md)