---
title: 'IDiaDataSource:: loadAndValidateDataFromPdb |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadAndValidateDataFromPdb method
ms.assetid: d66712dd-6c24-4192-919a-cce262066f0e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 97afff946827c37ec2f84457016525377977dc8b
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745003"
---
# <a name="idiadatasourceloadandvalidatedatafrompdb"></a>IDiaDataSource::loadAndValidateDataFromPdb
プログラムデータベース (.pdb) ファイルが、指定された署名情報と一致することを確認し、デバッグデータソースとして .pdb ファイルを準備します。

## <a name="syntax"></a>構文

```C++
HRESULT loadAndValidateDataFromPdb ( 
   LPCOLESTR pdbPath,
   GUID*     pcsig70,
   DWORD     sig,
   DWORD     age
);
```

#### <a name="parameters"></a>パラメーター
`pdbPath`

から.Pdb ファイルへのパス。

`pcsig70`

から.Pdb ファイルの署名に対して検証する GUID 署名。 @No__t_0 以降の .pdb ファイルにのみ、GUID シグネチャがあります。

`sig`

から.Pdb ファイルの署名に対して検証する32ビット署名。

`age`

から確認する有効期間の値。 Age は必ずしも既知の時刻値に対応しているわけではありません。 .pdb ファイルが対応する .exe ファイルと同期していないかどうかを判断するために使用されます。

## <a name="return-value"></a>戻り値
成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。 次の表に、このメソッドで使用できる戻り値を示します。

|[値]|説明|
|-----------|-----------------|
|E_PDB_NOT_FOUND|ファイルを開くことができませんでした。または、ファイルの形式が無効です。|
|E_PDB_FORMAT|古い形式のファイルにアクセスしようとしました。|
|E_PDB_INVALID_SIG|署名が一致しません。|
|E_PDB_INVALID_AGE|年齢が一致しません。|
|E_INVALIDARG|無効なパラメーター。|
|E_UNEXPECTED|データソースは既に準備されています。|

## <a name="remarks"></a>Remarks
.Pdb ファイルには、署名と有効期間の両方の値が含まれています。 これらの値は、.pdb ファイルまたは .pdb ファイルに一致する .exe ファイルまたは .dll ファイルにレプリケートされます。 このメソッドは、データソースを準備する前に、指定した .pdb ファイルの署名と有効期間が指定された値と一致することを確認します。

検証せずに .pdb ファイルを読み込むには、 [IDiaDataSource:: loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)メソッドを使用します。

(コールバックメカニズムを使用して) データ読み込みプロセスにアクセスするには、 [IDiaDataSource:: loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)メソッドを使用します。

メモリから .pdb ファイルを直接読み込むには、 [IDiaDataSource:: loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)メソッドを使用します。

## <a name="example"></a>例

```C++
IDiaDataSource* pSource;  // Previously created data source.
DEFINE_GUID(expectedGUIDSignature,0x1234,0x5678,0x01,0x02,0x03,0x04,0x05,0x06,0x07,0x08);
DWORD expectedFileSignature = 0x12345678;
DWORD expectedAge           = 128;

HRESULT hr;
hr = pSource->loadAndValidateDataFromPdb( L"yprog.pdb",
                                          &expectedGUIDSignature,
                                          expectedFileSignature,
                                          expectedAge);
if (FAILED(hr))
{
    // Report an error
}

```

## <a name="see-also"></a>関連項目
- [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)
- [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)
