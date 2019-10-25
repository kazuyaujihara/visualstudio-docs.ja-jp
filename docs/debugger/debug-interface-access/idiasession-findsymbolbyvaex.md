---
title: 'IDiaSession:: findSymbolByVAEx |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findSymbolByVAEx method
ms.assetid: 11c685f6-cda2-4474-a432-214ecaae4ffa
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 56dd91e76380bb4f43fae4f26d4124b2f9bc3ebf
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741984"
---
# <a name="idiasessionfindsymbolbyvaex"></a>IDiaSession::findSymbolByVAEx
指定した仮想アドレス (VA) とオフセットを格納している、またはそれに最も近いシンボルの種類を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findSymbolByVAEx ( 
   ULONGLONG    va,
   SymTagEnum   symtag,
   IDiaSymbol** ppSymbol,
   LONG*        displacement
);
```

#### <a name="parameters"></a>パラメーター
 `va`

からVA を指定します。

 `symtag`

から検索するシンボルの種類。 値は[Symtagenum](../../debugger/debug-interface-access/symtagenum.md)列挙型から取得されます。

 `ppSymbol`

入出力取得されたシンボルを表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクトを返します。

 `displacement`

入出力@No__t_0 によって指定された仮想アドレスからのオフセットを指定する値を返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="example"></a>例

```C++
IDiaSymbol* pFunc;
LONG disp = 0;
pSession->findSymbolByVAEx( va, SymTagFunction, &pFunc, &disp );
```

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)
- [IDiaSession::findSymbolByVA](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)