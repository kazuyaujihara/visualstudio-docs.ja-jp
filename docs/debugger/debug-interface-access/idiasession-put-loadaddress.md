---
title: IDiaSession::p ut_loadAddress |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::put_loadAddress method
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 39db3bc0e0107e734f5de3f6902a2ca0fcc55bb0
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741890"
---
# <a name="idiasessionput_loadaddress"></a>IDiaSession::put_loadAddress
このシンボルストア内のシンボルに対応する実行可能ファイルの読み込みアドレスを設定します。

## <a name="syntax"></a>構文

```C++
HRESULT put_loadAddress ( 
   ULONGLONG NewVal
);
```

#### <a name="parameters"></a>パラメーター
 `NewVal`

から実行可能ファイルのアドレスを読み込みます。

## <a name="remarks"></a>Remarks
 シンボル仮想アドレス (VA) のプロパティは、このメソッドの値を使用して計算されます。 このプロパティがゼロ以外に設定されている場合を除き、仮想アドレスは計算されません。

> [!NOTE]
> シンボルに対して仮想プロパティを使用する必要がある場合は、 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)オブジェクトを取得し、オブジェクトの使用を開始する前に、このメソッドを呼び出す必要があります。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)