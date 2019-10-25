---
title: IDiaLoadCallback2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback2 interface
ms.assetid: 9a44277d-cbed-4811-9bad-5a2aa0f09323
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7db8b6a115acdafeca2e7e0adbe11be97834cd6d
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742956"
---
# <a name="idialoadcallback2"></a>IDiaLoadCallback2
DIA シンボル検索プロシージャからコールバックを受信し、特定のプロセスに制限を適用できるようにします。

## <a name="syntax"></a>構文

```
IDiaLoadCallback2 : IDiaLoadCallback
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 このインターフェイスは、 [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md)インターフェイスのメソッドに加えて、次のメソッドを公開します。

|メソッド|説明|
|------------|-----------------|
|[IDiaLoadCallback2::RestrictOriginalPathAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictoriginalpathaccess.md)|元のデバッグディレクトリで .pdb ファイルを検索するかどうかを決定します。|
|[IDiaLoadCallback2::RestrictReferencePathAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictreferencepathaccess.md)|.Exe ファイルが配置されているパスで .pdb ファイルを検索するかどうかを決定します。|
|[IDiaLoadCallback2::RestrictDBGAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictdbgaccess.md)|Dbg ファイルからデバッグ情報を検索できるかどうかを決定します。|
|[IDiaLoadCallback2::RestrictSystemRootAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictsystemrootaccess.md)|.Pdb ファイルの検索がシステムルートディレクトリで許可されているかどうかを判断します。|

## <a name="remarks"></a>Remarks
 クライアントアプリケーションは、このインターフェイスを実装し、 [IDiaDataSource:: loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)メソッドの呼び出しでこのインターフェイスへの参照を提供します。 [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md)インターフェイスのすべてのメソッドを実装することも忘れないでください。

## <a name="requirements"></a>［要件］
 ヘッダー: Dia2

 ライブラリ: diaguids

 DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)
- [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)
- [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md)