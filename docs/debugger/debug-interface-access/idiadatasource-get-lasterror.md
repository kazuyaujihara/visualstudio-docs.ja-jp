---
title: 'IDiaDataSource:: get_lastError |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::get_lastError method
ms.assetid: cf08850b-8b75-4e8c-90bd-bd0214756f99
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 48595dda70560f555533a1857f73db4d7bd20a86
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744974"
---
# <a name="idiadatasourceget_lasterror"></a>IDiaDataSource::get_lastError
前回の読み込みエラーのファイル名を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_lastError (
   BSTR* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 の場合は、

入出力最後の読み込みエラーに関連付けられた .pdb ファイル名を含む文字列を返します。

## <a name="return-value"></a>戻り値
 読み込み操作によって発生した最後のエラーコードを返します。 @No__t_1 パラメーターが `NULL` 場合は `E_INVALIDARG` を返します。

## <a name="example"></a>例

```C++
BSTR    fileName;
HRESULT errorCode = pSource->get_lastError( &fileName );
```

## <a name="see-also"></a>関連項目
- [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)