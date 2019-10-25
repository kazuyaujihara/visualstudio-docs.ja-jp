---
title: 'IDiaSession:: Findシンボル Byaddr |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findSymbolByAddr method
ms.assetid: c130abc5-4d0a-4d2d-8286-94fde36ddd4a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ae0bab8ec0561b65c22890c0e0bbfeb461364b5c
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742063"
---
# <a name="idiasessionfindsymbolbyaddr"></a>IDiaSession::findSymbolByAddr
指定したアドレスを含む、またはそれに最も近いシンボルの種類を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findSymbolByAddr ( 
   DWORD        isect,
   DWORD        offset,
   SymTagEnum   symtag,
   IDiaSymbol** ppSymbol
);
```

#### <a name="parameters"></a>パラメーター
 `isect`

からアドレスのセクション部分を指定します。

 `offset`

からアドレスのオフセットコンポーネントを指定します。

 `symtag`

から検索するシンボルの種類。 値は[Symtagenum](../../debugger/debug-interface-access/symtagenum.md)列挙型から取得されます。

 `ppSymbol`

入出力取得されたシンボルを表す[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="example"></a>例

```C++
IDiaSymbol* pFunc;
pSession->findSymbolByAddr( isect, offset, SymTagFunction, &pFunc );
```

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)