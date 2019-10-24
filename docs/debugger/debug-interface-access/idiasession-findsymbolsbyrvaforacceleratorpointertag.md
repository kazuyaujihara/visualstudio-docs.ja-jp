---
title: 'IDiaSession:: findSymbolsByRVAForAcceleratorPointerTag |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a073cc45-0c7b-417e-b5fc-a3b08beccdbc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: eb1b24d24de35de30b24937a6cfbf59d12f69482
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742003"
---
# <a name="idiasessionfindsymbolsbyrvaforacceleratorpointertag"></a>IDiaSession::findSymbolsByRVAForAcceleratorPointerTag
このメソッドは、対応するタグ値を指定して、指定された相対仮想アドレスで、指定された親アクセラレータのスタブ関数に含まれるシンボルの列挙体を返します。

## <a name="syntax"></a>構文

```C++
HRESULT findSymbolsByRVAForAcceleratorPointerTag ( 
   IDiaSymbol*           parent,
   DWORD                 tagValue,
   DWORD                 rva,
   IDiaEnumSymbols**     ppResult
);
```

#### <a name="parameters"></a>パラメーター
 `parent`

から検索対象のアクセラレータスタブ関数に対応する `IDiaSymbol`。

 `tagValue`

からポインターのタグ値。

 `rva`

から相対仮想アドレス。

 `ppResult`

入出力結果を使用して初期化される `IDiaEnumSymbols` インターフェイスポインターへのポインター。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 このメソッドは、アクセラレータスタブ関数に対応する `IDiaSymbol` インターフェイスでのみ呼び出します。

## <a name="see-also"></a>関連項目
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)