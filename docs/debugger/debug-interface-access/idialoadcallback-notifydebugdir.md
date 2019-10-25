---
title: 'IDiaLoadCallback:: NotifyDebugDir |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback::NotifyDebugDir method
ms.assetid: bd04e2f6-0dbf-4742-a556-96f2cd99aa19
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6618440cab9b9042ec371383f6c809ca1d0d11f7
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743086"
---
# <a name="idialoadcallbacknotifydebugdir"></a>IDiaLoadCallback::NotifyDebugDir
デバッグディレクトリが .exe ファイルで見つかったときに呼び出されます。

## <a name="syntax"></a>構文

```C++
HRESULT NotifyDebugDir ( 
   BOOL  fExecutable,
   DWORD cbData,
   BYTE  data[]
);
```

#### <a name="parameters"></a>パラメーター
 `fExecutable`

[in] デバッグディレクトリが (dbg ファイルではなく) 実行可能ファイルから読み取られる場合は `TRUE` します。

 `cbData`

からデバッグディレクトリ内のデータのバイト数。

 `data[]`

からデバッグディレクトリを使用して入力された配列。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。 通常、リターンコードは無視されます。

## <a name="remarks"></a>Remarks
 [IDiaDataSource:: loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)メソッドは、実行可能ファイルの処理中にデバッグディレクトリを検出すると、このコールバックを呼び出します。

 このメソッドを使用すると、.pdb ファイルに存在しないデバッグ情報をサポートするために、クライアントが実行可能ファイルやデバッグファイルをリバースエンジニアリングする必要がなくなります。 このデータを使用すると、クライアントは使用可能なデバッグ情報の種類と、実行可能ファイルまたは dbg ファイルのどちらに存在するかを認識できます。

 @No__t_0 メソッドは、シンボルの提供に必要なときに .pdb ファイルと dbg ファイルの両方を透過的に開くため、ほとんどのクライアントはこのコールバックを必要としません。

## <a name="see-also"></a>関連項目
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)