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
ms.openlocfilehash: c86a0e995e3336bc217bcc9ad0e7ce28a6434478
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56597141"
---
# <a name="idiareadexeatrvacallback"></a>IDiaReadExeAtRVACallback
相対仮想アドレスで指定された実行可能ファイルのバイト数を指定するクライアント アプリケーションを有効にします。

## <a name="syntax"></a>構文

```
IDiaReadExeAtRVACallback : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、メソッドの`IDiaReadExeAtRVACallback`します。

|メソッド|説明|
|------------|-----------------|
|[IDiaReadExeAtRVACallback::ReadExecutableAtRVA](../../debugger/debug-interface-access/idiareadexeatrvacallback-readexecutableatrva.md)|指定した数の指定された相対仮想アドレス (RVA) 実行可能ファイルからで始まるバイトを読み取ります。|

## <a name="remarks"></a>解説
 クライアント アプリケーションは、実行可能ファイルのファイルに相対仮想アドレスを使用して実行可能ファイルのバイト数を提供するために、このインターフェイスを実装します。 ファイルの絶対オフセットを使用するには、実装、 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)インターフェイス。

## <a name="notes-for-callers"></a>呼び出し元のノート
 このメソッドは、クライアント アプリケーションによって実装されに渡される、 [idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)メソッド、ファイルの読み取りの代替方法として。

## <a name="requirements"></a>要件
 ヘッダー: Dia2.h

 ライブラリ: diaguids.lib

 DLL: msdia80.dll

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)