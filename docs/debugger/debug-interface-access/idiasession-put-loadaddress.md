---
title: Idiasession::put_loadaddress |Microsoft Docs
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
ms.openlocfilehash: b768b06e0702f7929b402086dcc6e11918f3e683
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56630094"
---
# <a name="idiasessionputloadaddress"></a>IDiaSession::put_loadAddress
このシンボル ストアのシンボルに対応する実行可能ファイルの読み込みアドレスを設定します。

## <a name="syntax"></a>構文

```C++
HRESULT put_loadAddress ( 
   ULONGLONG NewVal
);
```

#### <a name="parameters"></a>パラメーター
 `NewVal`

[in]実行可能ファイルのアドレスをロードします。

## <a name="remarks"></a>解説
 シンボルの仮想アドレス (VA) プロパティは、このメソッドの値を使用して計算されます。 このプロパティは 0 以外設定されていない限り、仮想アドレスは計算されません。

> [!NOTE]
>  取得する場合は、このメソッドを呼び出す必要があります、 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)オブジェクトし、シンボルで任意の仮想プロパティを使用する必要がある場合、オブジェクトの使用を開始する前にします。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)