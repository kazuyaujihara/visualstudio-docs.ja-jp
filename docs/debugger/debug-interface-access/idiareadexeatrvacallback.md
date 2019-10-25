---
title: IDiaReadExeAtRVACallback |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtRVACallback interface
ms.assetid: b2892513-3952-4f99-9b98-60cb9b1fdc91
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2aee44ff3acc1d7423e19de8fd64be0e46d8e372
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742806"
---
# <a name="idiareadexeatrvacallback"></a>IDiaReadExeAtRVACallback
クライアントアプリケーションが、相対仮想アドレスによって指定された実行可能ファイルのバイトを提供できるようにします。

## <a name="syntax"></a>構文

```
IDiaReadExeAtRVACallback : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、`IDiaReadExeAtRVACallback` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaReadExeAtRVACallback::ReadExecutableAtRVA](../../debugger/debug-interface-access/idiareadexeatrvacallback-readexecutableatrva.md)|実行可能ファイルから、指定された相対仮想アドレス (RVA) を開始位置として、指定されたバイト数を読み取ります。|

## <a name="remarks"></a>Remarks
 クライアントアプリケーションは、相対仮想アドレスを使用して実行可能ファイルのバイトを実行可能ファイルに提供するために、このインターフェイスを実装します。 絶対ファイルオフセットを使用するには、 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)インターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 このメソッドは、クライアントアプリケーションによって実装され、ファイルを読み取るための別の方法として[IDiaDataSource:: loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)メソッドに渡されます。

## <a name="requirements"></a>［要件］
 ヘッダー: Dia2

 ライブラリ: diaguids

 DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)