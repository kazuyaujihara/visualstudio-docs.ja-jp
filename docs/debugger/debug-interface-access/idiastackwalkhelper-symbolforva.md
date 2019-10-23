---
title: 'IDiaStackWalkHelper:: シンボル Forva |Microsoft Docs'
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
ms.openlocfilehash: f646616fddc0e7727ef9e8e80d9c29fbcba6ebc0
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741318"
---
# <a name="idiastackwalkhelpersymbolforva"></a>IDiaStackWalkHelper::symbolForVA
指定した仮想アドレスを含むシンボルを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT symbolForVA( 
   ULONGLONG     va,
   IDiaSymbol**  ppSymbol
);
```

#### <a name="parameters"></a>パラメーター
 `va`

から要求されたシンボルに含まれる仮想アドレス。 シンボルは、`SymTagFunctionType` ( [Symtagenum 列挙](../../debugger/debug-interface-access/symtagenum.md)列挙の値) である必要があります。

 `ppSymbol`

入出力指定したアドレスにあるシンボルを表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)