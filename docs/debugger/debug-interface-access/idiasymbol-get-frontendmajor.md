---
title: Idiasymbol::get_frontendmajor |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_frontEndMajor method
ms.assetid: f8a067c5-3306-4fc5-bc20-8910a47ed504
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cde514dfb9d76954f8b1cd1adbe35ace10366791
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64779814"
---
# <a name="idiasymbolgetfrontendmajor"></a>IDiaSymbol::get_frontEndMajor
フロント エンドのメジャー バージョン番号を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_frontEndMajor ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]フロント エンドのメジャー バージョン番号を返します。 「解説」を参照してください。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
> 戻り値`S_FALSE`プロパティがシンボルを使用できないことを意味します。

## <a name="remarks"></a>Remarks
 コンパイラは通常の 2 つの主な要素で構成されます。 中間形式を解析してソース コードを処理するフロント エンド (パーサー) と、バック エンド (コード ジェネレーター) アセンブリに中間形式を変換します。 これは、フロント エンド、バックエンドとは異なるバージョンが珍しくありません。

 フロント エンドまたはバックエンドのバージョン番号は 3 つの部分で構成されます:\<メジャー >.\<マイナー >。\<ビルド > ここで、\<主要な >、メジャー バージョン番号は、\<マイナー > はマイナー バージョン番号、および\<ビルド > ビルド番号です。 例: 13.10.3077。

## <a name="requirements"></a>必要条件

|必要条件|説明|
|-----------------|-----------------|
|ヘッダー:|Dia2.h|
|バージョン:|DIA SDK v7.0|

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)