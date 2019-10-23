---
title: IDiaReadExeAtOffsetCallback |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtOffsetCallback interface
ms.assetid: 3c961641-3ce3-4bc3-bd6e-a802fa3bec49
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f8498b0189a1d5bfb876417d4719adb3487065d5
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742810"
---
# <a name="idiareadexeatoffsetcallback"></a>IDiaReadExeAtOffsetCallback
クライアントアプリケーションが、ファイルの位置によって指定された実行可能ファイルのバイトを提供できるようにします。

## <a name="syntax"></a>構文

```
IDiaReadExeAtOffsetCallback : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、`IDiaReadExeAtOffsetCallback` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaReadExeAtOffsetCallback::ReadExecutableAt](../../debugger/debug-interface-access/idiareadexeatoffsetcallback-readexecutableat.md)|実行可能ファイルから指定されたオフセットを開始位置として、指定されたバイト数を読み取ります。|

## <a name="remarks"></a>Remarks
 クライアントアプリケーションは、実行可能ファイルに絶対オフセットを使用して実行可能ファイルのバイトを提供するために、このインターフェイスを実装します。 相対仮想アドレスを使用するには、 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)インターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 このメソッドは、クライアントアプリケーションによって実装され、ファイルを読み取るための別の方法として[IDiaDataSource:: loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)メソッドに渡されます。

## <a name="requirements"></a>［要件］
 ヘッダー: Dia2

 ライブラリ: diaguids

 DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)