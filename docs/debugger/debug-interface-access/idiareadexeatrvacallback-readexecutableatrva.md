---
title: IDiaReadExeAtRVACallback::ReadExecutableAtRVA | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtRVACallback::ReadExecutableAtRVA method
ms.assetid: 3c1e965f-8f05-41a8-86d8-01830b2377c9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cf423ddc91926fb04adac849783b7c26b4c4f720
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62828470"
---
# <a name="idiareadexeatrvacallbackreadexecutableatrva"></a>IDiaReadExeAtRVACallback::ReadExecutableAtRVA
指定した数の指定された相対仮想アドレス (RVA) 実行可能ファイルからで始まるバイトを読み取ります。

## <a name="syntax"></a>構文

```C++
HRESULT ReadExecutableAtRVA ( 
   DWORD  relativeVirtualAddress,
   DWORD  cbData,
   DWORD* pcbData,
   BYTE   data[]
);
```

#### <a name="parameters"></a>パラメーター
 `relativeVirtualAddress`

[in]読み取りを開始する実行可能ファイルの rva を示します。

 `cbData`

[in]読み取るバイト数。

 `pcbData`

[out]読み取られたバイト数を返します。

 `data[]`

[入力、出力]ファイルから読み取られたバイトに設定している配列。

## <a name="remarks"></a>Remarks
 このメソッドは DIA のサポート コード相対仮想アドレスを使用して実行可能ファイルからデータのバイト数を読み込めません。 サポートにこのメソッドは、 [idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)メソッド。

## <a name="see-also"></a>関連項目
- [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)