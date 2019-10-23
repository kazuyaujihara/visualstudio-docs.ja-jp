---
title: 'IDiaSession:: Findシンボル Bytoken |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findSymbolByToken method
ms.assetid: 3c92149c-6eef-454f-86be-66e89557b9e6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 098d84d6c7c79fee5fea5e5b2b36136bf7b55b26
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742024"
---
# <a name="idiasessionfindsymbolbytoken"></a>IDiaSession::findSymbolByToken
指定したメタデータトークンを含むシンボルを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findSymbolByToken ( 
   ULONG        token,
   SymTagEnum   symtag,
   IDiaSymbol** ppSymbol
);
```

#### <a name="parameters"></a>パラメーター
 `token`

からトークンを指定します。

 `symtag`

から検索するシンボルの種類。 値は[Symtagenum](../../debugger/debug-interface-access/symtagenum.md)列挙型から取得されます。

 `ppSymbol`

入出力取得されたシンボルを表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="example"></a>例

```C++
IDiaSymbol* pFunc;
pSession->findSymbolByToken( token, SymTagFunction, &pFunc );
```

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)