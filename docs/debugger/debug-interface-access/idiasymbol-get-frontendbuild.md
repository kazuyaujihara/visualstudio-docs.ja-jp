---
title: Idiasymbol::get_frontendbuild |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_frontEndBuild method
ms.assetid: f7dab1c6-112b-4966-baa5-afc976949c76
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8af52d36370d8778c38c2ddead446d66b5d46eba
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64803216"
---
# <a name="idiasymbolgetfrontendbuild"></a>IDiaSymbol::get_frontEndBuild
フロント エンドのビルド番号を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_frontEndBuild ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]フロント エンドのビルド番号を返します。 「解説」を参照してください。

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