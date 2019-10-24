---
title: 'IDiaPropertyStorage:: ReadMultiple |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadMultiple
ms.assetid: 6ccc9397-ce41-4f72-b261-72ac252cd4a5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9cd1e419e1d08120274fc627a672eb52331ca50f
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742883"
---
# <a name="idiapropertystoragereadmultiple"></a>IDiaPropertyStorage::ReadMultiple
指定されたプロパティを現在のプロパティセットから読み取ります。

## <a name="syntax"></a>構文

```C++
HRESULT ReadMultiple( 
   ULONG          cpspec,
   PROPSPEC const rgpspec,
   PROPVARIANT    rgvar
);
```

#### <a name="parameters"></a>パラメーター
 `cpspec`

から@No__t_0 配列に指定されたプロパティの数。 0の場合、メソッドはプロパティを返しませんが、成功コードとして `S_OK` を返します。

 `rgpspec`

から読み取るプロパティの配列。 プロパティは、プロパティ ID または省略可能な文字列名のいずれかで指定できます。 配列内の特定の順序でプロパティを指定する必要はありません。 配列には重複するプロパティを含めることができます。その結果、単純なプロパティに対して戻り値のプロパティ値が重複します。 非単純なプロパティは、2回目に開こうとしたときにアクセスが拒否されたことを返します。 配列には、プロパティ Id と文字列 Id の組み合わせを含めることができます。 この配列には、少なくとも `cpspec` のプロパティ値が必要です。

 `rgvar`

[入力、出力]各プロパティの値が格納される `PROPVARIANT` 構造体の配列 (VisualStudio 名前空間内) を指定します。 配列は、少なくとも `cpspec` の要素のサイズにする必要があります。 呼び出し元は、配列内の値を初期化する必要はありません。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 1つ以上のプロパティが見つからなかった場合に `S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 プロパティが見つからなかった場合は、`rgvar` 配列内の対応するエントリに `VT_EMPTY` の型の `VARIANT` が格納されます。

## <a name="see-also"></a>関連項目
- [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)