---
title: Idiastackwalkhelper::symbolforva |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper::symbolForVA method
ms.assetid: 8dd9455d-d44c-4dd6-a0aa-31131cbea2aa
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 01c457947eb84859f2ce92378688dd03c624c86d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62837889"
---
# <a name="idiastackwalkhelpersymbolforva"></a>IDiaStackWalkHelper::symbolForVA
指定した仮想アドレスを表すシンボルを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT symbolForVA( 
   ULONGLONG     va,
   IDiaSymbol**  ppSymbol
);
```

#### <a name="parameters"></a>パラメーター
 `va`

[in]要求されたシンボルが含まれている仮想アドレス。 シンボルがある必要があります、 `SymTagFunctionType` (からの値、 [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)列挙型)。

 `ppSymbol`

[out][IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)指定のアドレスにあるシンボルを表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)