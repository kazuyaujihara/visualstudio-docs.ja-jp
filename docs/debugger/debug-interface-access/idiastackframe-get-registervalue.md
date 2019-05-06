---
title: Idiastackframe::get_registervalue |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_registerValue method
ms.assetid: cbe3d8ac-319a-40ac-bc3e-4eb81b2d7807
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a819293863b658f6e12609b2c1cd83c37532e02d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62832106"
---
# <a name="idiastackframegetregistervalue"></a>IDiaStackFrame::get_registerValue
スタック フレームに格納されている、指定されたレジスタの値を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_registerValue(
   ULONG      registerIndex,
   ULONGLONG *pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `registerIndex`

[in]1 つ、 [CV_HREG_e 列挙型](../../debugger/debug-interface-access/cv-hreg-e.md)列挙値。

 `pRetVal`

[out]レジスタに格納される値。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
- [CV_HREG_e 列挙型](../../debugger/debug-interface-access/cv-hreg-e.md)