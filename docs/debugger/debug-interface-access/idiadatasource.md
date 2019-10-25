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
ms.openlocfilehash: 453be1d77f1d2b1759e3de4433225cf97d026054
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744913"
---
# <a name="idiadatasource"></a>IDiaDataSource
デバッグシンボルのソースへのアクセスを開始します。

## <a name="syntax"></a>構文

```
IDiaDataSource : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
次の表は、`IDiaDataSource` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaDataSource::get_lastError](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md)|前回の読み込みエラーのファイル名を取得します。|
|[IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)|プログラムデータベース (.pdb) ファイルをデバッグデータソースとして開き、準備します。|
|[IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)|プログラムデータベース (.pdb) ファイルが、指定された署名情報と一致することを開き、確認します.pdb ファイルをデバッグデータソースとして準備します。|
|[IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)|を開き、.exe/.dll ファイルに関連付けられているデバッグデータを準備します。|
|[IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)|メモリ内データストリームを介してアクセスされるプログラムデータベース (.pdb) ファイルに格納されているデバッグデータを準備します。|
|[IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)|シンボルに対してクエリを実行するためのセッションを開きます。|

## <a name="remarks"></a>Remarks
@No__t_0 インターフェイスの load メソッドのいずれかを呼び出すと、シンボルソースが開きます。 [IDiaDataSource:: openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)メソッドの呼び出しが成功すると、データソースのクエリをサポートする[IDiaSession](../../debugger/debug-interface-access/idiasession.md)インターフェイスが返されます。 Load メソッドがファイルに関連するエラーを返す場合、 [IDiaDataSource:: get_lastError](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md)メソッドの戻り値には、エラーに関連付けられているファイル名が含まれます。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
このインターフェイスは、クラス識別子 `CLSID_DiaSource` と `IID_IDiaDataSource` のインターフェイス ID を使用して `CoCreateInstance` 関数を呼び出すことによって取得されます。 この例は、このインターフェイスを取得する方法を示しています。

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

## <a name="requirements"></a>［要件］
ヘッダー: Dia2

ライブラリ: diaguids

DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
