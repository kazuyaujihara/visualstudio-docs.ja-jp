---
title: IDiaLoadCallback |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback interface
ms.assetid: 2f18c64c-2cf0-43fc-a447-21e82702ca2a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0ca58a206fec15bb8a9ae7f68a278a4530be47d8
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743040"
---
# <a name="idialoadcallback"></a>IDiaLoadCallback
DIA シンボル検索プロシージャからコールバックを受信します。これにより、ユーザーインターフェイスは、場所の試行の進行状況についてレポートすることができます。

## <a name="syntax"></a>構文

```
IDiaLoadCallback : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 このインターフェイスでは、次のメソッドが公開されています。

|メソッド|説明|
|------------|-----------------|
|[IDiaLoadCallback::NotifyDebugDir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)|デバッグディレクトリが .exe ファイルで見つかったときに呼び出されます。|
|[IDiaLoadCallback::NotifyOpenDBG](../../debugger/debug-interface-access/idialoadcallback-notifyopendbg.md)|Dbg ファイルが開かれたときに呼び出されます。|
|[IDiaLoadCallback::NotifyOpenPDB](../../debugger/debug-interface-access/idialoadcallback-notifyopenpdb.md)|任意の .pdb ファイルが開かれたときに呼び出されます。|
|[IDiaLoadCallback::RestrictRegistryAccess](../../debugger/debug-interface-access/idialoadcallback-restrictregistryaccess.md)|シンボル検索パスを検索するためにレジストリクエリを使用できるかどうかを決定します。|
|[IDiaLoadCallback::RestrictSymbolServerAccess](../../debugger/debug-interface-access/idialoadcallback-restrictsymbolserveraccess.md)|シンボルを解決するために、シンボルサーバーへのアクセスが許可されているかどうかを判断します。|

## <a name="remarks"></a>Remarks
 クライアントアプリケーションは、このインターフェイスを実装し、 [IDiaDataSource:: loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)メソッドの呼び出しでこのインターフェイスへの参照を提供します。

 読み込みプロセスに適用できるその他の制限については、 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)インターフェイスを参照してください。

## <a name="requirements"></a>［要件］
 ヘッダー: Dia2

 ライブラリ: diaguids

 DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)
- [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)