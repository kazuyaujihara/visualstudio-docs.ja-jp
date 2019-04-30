---
title: Idiasymbol::get_virtualtableshape |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_virtualTableShape method
ms.assetid: 92360cbd-0761-446e-93f9-04dc8f4b66c6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8dfc91a63634f47cc2a8bc16d0dfbede1e14abf4
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63386569"
---
# <a name="idiasymbolgetvirtualtableshape"></a>IDiaSymbol::get_virtualTableShape
ユーザー定義型の仮想テーブルの型のシンボルのインターフェイスを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_virtualTableShape ( 
   IDiaSymbol** pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]返します、 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)ユーザー定義型の仮想テーブルを表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)