---
title: Idiasymbol::get_msil |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_msil method
ms.assetid: 43a8e003-6856-4726-aa16-c0d4dae7299b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b502d1504c5a61ed073ed77eed76dd5f7c139a35
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64784361"
---
# <a name="idiasymbolgetmsil"></a>IDiaSymbol::get_msil
シンボルが Microsoft Intermediate Language (MSIL) コードを参照するかどうかを指定するフラグを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_msil ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]返します`TRUE`シンボルが MSIL コードを指す場合、それ以外の場合、返されます`FALSE`します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)