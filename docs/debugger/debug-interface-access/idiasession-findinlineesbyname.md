---
title: 'IDiaSession:: findInlineesByName |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 9860336d-f703-4ecb-bfc4-3f5beb175a76
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a7fd74707284e32471bad1da27e288139ea617a1
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742176"
---
# <a name="idiasessionfindinlineesbyname"></a>IDiaSession::findInlineesByName
指定した名前に一致するすべてのインライン関数の行番号情報をクライアントが反復処理できるようにする列挙体を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findInlineesByName ( 
   LPCOLESTR             name,
   DWORD                 option,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `name`

から比較に使用する名前を指定します。

 `option`

から名前検索に適用される比較オプションを指定します。 [Namesearchoptions 列挙](../../debugger/debug-interface-access/namesearchoptions.md)列挙の値は、単独で、または組み合わせて使用できます。

 `ppResult`

入出力取得された行番号の一覧を含む[IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)