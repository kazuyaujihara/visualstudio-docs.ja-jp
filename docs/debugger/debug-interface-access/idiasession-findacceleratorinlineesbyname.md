---
title: IDiaSession::findAcceleratorInlineesByName |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e203e5c2-6563-43fa-be56-3063955043ab
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fb3caa5574605864a0dd16b59b6f451530b8e631
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62827791"
---
# <a name="idiasessionfindacceleratorinlineesbyname"></a>IDiaSession::findAcceleratorInlineesByName
指定されたインライン関数の名前に対応するインライン フレームのシンボルの列挙を返します。

## <a name="syntax"></a>構文

```C++
HRESULT findAcceleratorInlineeLinesByName ( 
   LPCOLESTR             name,
   DWORD                 option,
   IDiaEnumSymbols**     ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `name`

[in]検索するインライン関数の名前。

 `option`

[in]対応しているフレームのインラインの検索時に使用される名前の検索オプション`name`します。 詳細については、次を参照してください。 [NameSearchOptions 列挙型](../../debugger/debug-interface-access/namesearchoptions.md)します。

 `ppResult`

[out]ポインター、`IDiaEnumSymbols`インターフェイス ポインターでは、結果を使用して初期化します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 この関数はインラインに起因アクセラレータ スタブ関数内でのみを検索します。 ネイティブ C++ プロシージャ レコードは無視されます。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)