---
title: 'IDiaStackFrame:: get_cplusplusExceptionHandling |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_cplusplusExceptionHandling method
ms.assetid: f2631820-c986-40ca-b61e-230d7a9c426c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d78a4c73d7954f48c87c1eafec4d0b35fc1292ef
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741755"
---
# <a name="idiastackframeget_cplusplusexceptionhandling"></a>IDiaStackFrame::get_cplusplusExceptionHandling
例外処理が有効かどうC++かを示すフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_cplusplusExceptionHandling ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力このフレームにC++対して例外処理が有効になっている場合は `TRUE` を返します。それ以外の場合は `FALSE` を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 プロパティがサポートされていない場合は `S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 C++例外処理は、構造化例外処理またはシステム例外処理と同じではありません。

 構造化例外処理が有効かどうかを判断するには、 [IDiaStackFrame:: get_systemExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-systemexceptionhandling.md)メソッドを呼び出します。

## <a name="see-also"></a>関連項目
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
- [IDiaStackFrame::get_systemExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-systemexceptionhandling.md)