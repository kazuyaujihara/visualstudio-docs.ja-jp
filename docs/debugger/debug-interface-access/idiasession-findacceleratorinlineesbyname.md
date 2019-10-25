---
title: 'IDiaSession:: findAcceleratorInlineesByName |Microsoft Docs'
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
ms.openlocfilehash: 007477d3f0de3767b0c5ef0af977f969505884ed
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742309"
---
# <a name="idiasessionfindacceleratorinlineesbyname"></a>IDiaSession::findAcceleratorInlineesByName
指定されたインライン関数名に対応するインラインフレームのシンボルの列挙体を返します。

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

から検索するインライン関数の名前。

 `option`

から@No__t_0 に対応するインラインフレームを検索するときに使用する名前検索オプション。 詳細については、「 [Namesearchoptions 列挙型](../../debugger/debug-interface-access/namesearchoptions.md)」を参照してください。

 `ppResult`

入出力結果を使用して初期化される `IDiaEnumSymbols` インターフェイスポインターへのポインター。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 この関数は、アクセラレータスタブ関数内でのみインラインを検索します。 ネイティブC++プロシージャレコードは無視されます。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)