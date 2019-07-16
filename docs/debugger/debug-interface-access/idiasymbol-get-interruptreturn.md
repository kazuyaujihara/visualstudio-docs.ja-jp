---
title: Idiasymbol::get_interruptreturn |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_interruptReturn method
ms.assetid: 9665da6c-4cc0-41d7-b2e2-0d9e50174cf8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 87a0938be403d3818d1b399409f91d33067f805b
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64832773"
---
# <a name="idiasymbolgetinterruptreturn"></a>IDiaSymbol::get_interruptReturn
関数に割り込み命令からの戻り値が含まれるかどうかを指定するフラグを取得します (たとえば、X86 アセンブリ コード`iret`)。

## <a name="syntax"></a>構文

```C++
HRESULT get_interruptReturn(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>パラメーター
 `pFlag`

[out]返します`TRUE`場合は、関数は割り込み命令からの戻り値を返しますそれ以外の場合、`FALSE`します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティがシンボルを使用できないことを意味します。

## <a name="requirements"></a>必要条件

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|Dia2.h|
|バージョン:|DIA SDK バージョン 8.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)