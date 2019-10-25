---
title: 'IDiaSession:: findFile |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findFile method
ms.assetid: a215dc21-b316-40d7-9923-55bfa014976b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d9751127007b4e7823cf6d2ae35ed2fe80cb83b8
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742277"
---
# <a name="idiasessionfindfile"></a>IDiaSession::findFile
コンパイル単位と名前を指定してソースファイルを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findFile ( 
   IDiaSymbol*           pCompiland,
   LPCOLESTR             name,
   DWORD                 option,
   IDiaEnumSourceFiles** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `pCompiland`

から検索のコンテキストとして使用されるコンパイル単位を表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクト。 すべての compilands でソースファイルを検索するには、このパラメーターを `NULL` に設定します。

 `name`

から取得するソースファイルの名前を指定します。 すべてのソースファイルを取得するには、このパラメーターを `NULL` に設定します。

 `option`

から名前検索に適用される比較オプションを指定します。 [Namesearchoptions 列挙](../../debugger/debug-interface-access/namesearchoptions.md)列挙の値は、単独で、または組み合わせて使用できます。

 `ppResult`

入出力取得したソースファイルのリストを格納している[IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="example"></a>例

```C++
IDiaEnumSourceFiles* pEnum;
pSession->findFile( NULL, L"sourcefile.cpp", nsFNameExt, &pEnum );
```

## <a name="see-also"></a>関連項目
- [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [NameSearchOptions 列挙型](../../debugger/debug-interface-access/namesearchoptions.md)