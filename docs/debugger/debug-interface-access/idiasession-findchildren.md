---
title: 'IDiaSession:: findChildren |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findChildren method
ms.assetid: 5d19046f-f668-4aa9-8788-95cda9a98997
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cca6778e5697c5f8821322c19d706d733d7f2b9f
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742298"
---
# <a name="idiasessionfindchildren"></a>IDiaSession::findChildren
名前と記号の種類に一致する指定された親識別子のすべての子を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findChildren ( 
   IDiaSymbol*       parent,
   SymTagEnum        symtag,
   LPCOLESTR         name,
   DWORD             compareFlags,
   IDiaEnumSymbols** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `parent`

から親を表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクト。 この親シンボルが関数、モジュール、またはブロックの場合、その構文の子が `ppResult` に返されます。 親シンボルが型の場合は、その子クラスが返されます。 このパラメーターが `NULL` 場合、`symtag` は `SymTagExe` または `SymTagNull` に設定する必要があります。これにより、グローバルスコープ (.exe ファイル) が返されます。

 `symtag`

から取得する子のシンボルタグを指定します。 値は[Symtagenum](../../debugger/debug-interface-access/symtagenum.md)列挙型から取得されます。 すべての子を取得するには、を `SymTagNull` に設定します。

 `name`

から取得する子の名前を指定します。 すべての子を取得するには、を `NULL` に設定します。

 `compareFlags`

から名前の一致に適用される比較オプションを指定します。 [Namesearchoptions 列挙](../../debugger/debug-interface-access/namesearchoptions.md)列挙の値は、単独で、または組み合わせて使用できます。

 `ppResult`

入出力取得した子シンボルのリストを格納している[IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="example"></a>例
 次の例では、`szVarName` 名前に一致する関数 `pFunc` のローカル変数を検索する方法を示します。

```C++
IDiaEnumSymbols* pEnum;
pSession->findChildren( pFunc, SymTagData, szVarName, nsCaseSensitive, &pEnum );
```

## <a name="see-also"></a>関連項目
- [概要](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [NameSearchOptions 列挙型](../../debugger/debug-interface-access/namesearchoptions.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)