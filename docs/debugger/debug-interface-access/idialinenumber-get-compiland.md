---
title: 'IDiaLineNumber:: get_compiland |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_compiland method
ms.assetid: c476d0b8-c473-47eb-96f5-c4e8f577b1c9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8d6ae842d4717bdc0bd989327f07d9566d1161b8
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743229"
---
# <a name="idialinenumberget_compiland"></a>IDiaLineNumber::get_compiland
イメージテキストのバイトを提供するコンパイル単位のシンボルへの参照を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_compiland ( 
   IDiaSymbol** pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 の場合は、

入出力イメージテキストのバイトを提供したコンパイル単位の[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)