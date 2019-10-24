---
title: 'IDiaDataSource:: loadDataFromPdb |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadDataFromPdb method
ms.assetid: 02159073-8144-47f8-a0b0-aa0edcb92b5b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7526ba6e62c9df22a2338adc80f5d56578502cdb
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744934"
---
# <a name="idiadatasourceloaddatafrompdb"></a>IDiaDataSource::loadDataFromPdb
プログラムデータベース (.pdb) ファイルをデバッグデータソースとして開き、準備します。

## <a name="syntax"></a>構文

```C++
HRESULT loadDataFromPdb (
   LPCOLESTR pdbPath
);
```

#### <a name="parameters"></a>パラメーター
pdbPath

から.Pdb ファイルへのパス。

## <a name="return-value"></a>戻り値
成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。 次の表に、このメソッドで使用できる戻り値を示します。

|[値]|説明|
|-----------|-----------------|
|E_PDB_NOT_FOUND|ファイルを開くことができなかったか、ファイルの形式が無効であると判断されました。|
|E_PDB_FORMAT|古い形式のファイルにアクセスしようとしました。|
|E_INVALIDARG|無効なパラメーター。|
|E_UNEXPECTED|データソースは既に準備されています。|

## <a name="remarks"></a>Remarks
このメソッドは、.pdb ファイルから直接デバッグデータを読み込みます。

特定の条件に対して .pdb ファイルを検証するには、 [IDiaDataSource:: loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)メソッドを使用します。

(コールバックメカニズムを使用して) データ読み込みプロセスにアクセスするには、 [IDiaDataSource:: loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)メソッドを使用します。

メモリから .pdb ファイルを直接読み込むには、 [IDiaDataSource:: loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)メソッドを使用します。

## <a name="example"></a>例

```C++
HRESULT hr = pSource->loadDataFromPdb( L"myprog.pdb" );
if (FAILED(hr))
{
    // report error
}
```

## <a name="see-also"></a>関連項目
- [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)
- [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)
