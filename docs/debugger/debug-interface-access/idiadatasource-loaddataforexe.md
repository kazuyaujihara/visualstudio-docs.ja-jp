---
title: 'IDiaDataSource:: loadDataForExe |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadDataForExe method
ms.assetid: d94a1068-f53f-44b5-b6fb-00dec361a7f2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7a86abb00ebc090c37f03a5533376ae0b9c3e8ae
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744955"
---
# <a name="idiadatasourceloaddataforexe"></a>IDiaDataSource::loadDataForExe
を開き、.exe/.dll ファイルに関連付けられているデバッグデータを準備します。

## <a name="syntax"></a>構文

```C++
HRESULT loadDataForExe (
   LPCOLESTR executable,
   LPCOLESTR searchPath,
   IUnknown* pCallback
);
```

#### <a name="parameters"></a>パラメーター
executable

から.Exe ファイルまたは .dll ファイルへのパス。

searchPath

からデバッグデータを検索する代替パス。

pCallback

から[IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md)、 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)、 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)、 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)の各インターフェイスなど、デバッグのコールバックインターフェイスをサポートするオブジェクトの `IUnknown` インターフェイス。

## <a name="return-value"></a>戻り値
成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。 次の表に、このメソッドで使用できるエラーコードをいくつか示します。

|[値]|説明|
|-----------|-----------------|
|E_PDB_NOT_FOUND|ファイルを開くことができませんでした。または、ファイルの形式が無効です。|
|E_PDB_FORMAT|古い形式のファイルにアクセスしようとしました。|
|E_PDB_INVALID_SIG|署名が一致しません。|
|E_PDB_INVALID_AGE|年齢が一致しません。|
|E_INVALIDARG|無効なパラメーター。|
|E_UNEXPECTED|データソースは既に準備されています。|

## <a name="remarks"></a>Remarks
.Exe/.dll ファイルのデバッグヘッダーは、関連付けられたデバッグデータの場所に名前を付けます。

このメソッドは、デバッグヘッダーを読み取り、デバッグデータを検索して準備します。 検索の進行状況は、必要に応じて、コールバックを使用して報告および制御することができます。 たとえば、 [IDiaLoadCallback:: NotifyDebugDir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)は、`IDiaDataSource::loadDataForExe` メソッドがデバッグディレクトリを検出して処理するときに呼び出されます。

[IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)インターフェイスと[IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)インターフェイスを使用すると、クライアントアプリケーションは、標準によってファイルに直接アクセスできない場合に、実行可能ファイルからデータを読み取るための別の方法を提供できます。ファイル i/o。

検証せずに .pdb ファイルを読み込むには、 [IDiaDataSource:: loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)メソッドを使用します。

特定の条件に対して .pdb ファイルを検証するには、 [IDiaDataSource:: loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)メソッドを使用します。

メモリから .pdb ファイルを直接読み込むには、 [IDiaDataSource:: loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)メソッドを使用します。

## <a name="example"></a>例

```C++
class MyCallBack: public IDiaLoadCallback
{
...
};
MyCallBack callback;
...
HRESULT hr = pSource->loadDataForExe( L"myprog.exe", L".\debug", (IUnknown*)&callback);
if (FAILED(hr))
{
    // Report error
}
```

## <a name="see-also"></a>関連項目
- [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)
- [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md)
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)
- [IDiaLoadCallback::NotifyDebugDir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)
- [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)
- [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)
- [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)
- [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)
- [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)
