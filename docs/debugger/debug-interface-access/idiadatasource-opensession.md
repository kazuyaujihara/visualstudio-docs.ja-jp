---
title: 'IDiaDataSource:: openSession |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::openSession method
ms.assetid: a3319ed0-3979-483b-9852-c0af96852c48
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7dd6ab61db3e3bafd594298aa41d32bce64d4941
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744920"
---
# <a name="idiadatasourceopensession"></a>IDiaDataSource::openSession
シンボルに対してクエリを実行するためのセッションを開きます。

## <a name="syntax"></a>構文

```C++
HRESULT openSession ( 
   IDiaSession** ppSession
);
```

#### <a name="parameters"></a>パラメーター
ppSession

入出力開いているセッションを表す[IDiaSession](../../debugger/debug-interface-access/idiasession.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。 次の表に、このメソッドで使用できる戻り値を示します。

|[値]|説明|
|-----------|-----------------|
|E_UNEXPECTED|[IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)オブジェクトは、以前はシンボルのソースで初期化されていません。|
|E_INVALIDARG|無効な `ppSession` パラメーター。|
|E_OUTOFMEMORY|セッションを開くためのメモリが不足しています。|

## <a name="remarks"></a>Remarks
このメソッドは、データソースの[IDiaSession](../../debugger/debug-interface-access/idiasession.md)オブジェクトを開きます。

`IDiaSession` オブジェクトは、データソースへのクエリを実装します。 セッションは、デバッグシンボルのセットごとに1つのアドレス空間を管理します。 データソースシンボルによって記述されている .exe ファイルまたは .dll ファイルが複数のアドレス範囲でアクティブになっている場合 (複数のプロセスが読み込まれている場合など)、各アドレス範囲に対して1つのセッションを使用する必要があります。

## <a name="example"></a>例

```C++
IDiaSession* pSession;
HRESULT hr = pSource->openSession( &pSession );
if (FAILED(hr))
{
   // report error
}
```

## <a name="see-also"></a>関連項目
- [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)
- [概要](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [.Pdb ファイルの照会](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)
