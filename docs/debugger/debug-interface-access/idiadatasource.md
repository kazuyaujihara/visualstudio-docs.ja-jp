---
title: IDiaDataSource |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource interface
ms.assetid: 6260ac76-4f9d-4144-ba22-32f8620b32c2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8b8618cc3484584430bbe3ae3fde59b6e5d5fc78
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56612362"
---
# <a name="idiadatasource"></a>IDiaDataSource
デバッグ シンボルのソースへのアクセスを開始します。

## <a name="syntax"></a>構文

```
IDiaDataSource : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
次の表は、メソッドの`IDiaDataSource`します。

|メソッド|説明|
|------------|-----------------|
|[IDiaDataSource::get_lastError](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md)|最後の読み込みエラーのファイル名を取得します。|
|[IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)|開き、デバッグのデータ ソースとしてのプログラム データベース (.pdb) ファイルを準備します。|
|[IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)|開き、プログラム データベース (.pdb) ファイルが提供されて署名情報と一致していることを確認します。デバッグのデータ ソースとしての .pdb ファイルを準備します。|
|[IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)|開き、.exe/.dll ファイルに関連付けられたデバッグ データを準備します。|
|[IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)|メモリ内のデータ ストリームを使用してアクセス プログラム データベース (.pdb) ファイルに格納されているデバッグ データを準備します。|
|[IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)|シンボルを照会するためのセッションを開きます。|

## <a name="remarks"></a>解説
Load メソッドの 1 つの呼び出し、`IDiaDataSource`インターフェイスは、シンボル ファイルを開きます。 呼び出しは成功、 [idiadatasource::opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md)メソッドが返す、 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)データ ソースの照会をサポートするインターフェイス。 Load メソッドは、ファイルに関連するエラーを返す場合、 [idiadatasource::get_lasterror](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md)メソッドを返す値には、エラーに関連付けられているファイル名が含まれています。

## <a name="notes-for-callers"></a>呼び出し元のノート
このインターフェイスは呼び出すことによって取得、`CoCreateInstance`クラス識別子を持つ関数`CLSID_DiaSource`とのインターフェイス ID`IID_IDiaDataSource`します。 この例では、このインターフェイスを取得する方法を示します。

## <a name="example"></a>例

```C++

      IDiaDataSource* pSource;
HRESULT hr = CoCreateInstance(CLSID_DiaSource,
                              NULL,
                              CLSCTX_INPROC_SERVER,
                              IID_IDiaDataSource,
                              (void**) &pSource);
if (FAILED(hr))
{
    // Report error and exit
}
```

## <a name="requirements"></a>要件
ヘッダー: Dia2.h

ライブラリ: diaguids.lib

DLL: msdia80.dll

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
