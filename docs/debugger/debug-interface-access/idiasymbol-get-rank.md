---
title: Idiasymbol::get_rank |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_rank method
ms.assetid: 14cc9c4b-a5ec-414a-b01f-4a142c17b7cc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 646672904aebb8e4c0fcdd5200b60c2a2349a859
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56639285"
---
# <a name="idiasymbolgetrank"></a>IDiaSymbol::get_rank
FORTRAN の多次元配列のランク (次元数) を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_rank ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]FORTRAN の多次元配列の次元数を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。

> [!NOTE]
>  戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。

## <a name="remarks"></a>解説
 ランクとして、配列が宣言されている配列の次元数を指す`myarray[1,2,3]`します。 この例では、3、3 つのディメンションのランクがあります。 ランクは、各次元の配列の配列の概念を使用する C++ には適用されません (つまり、 `myarray[1][2][3]`)。

## <a name="see-also"></a>関連項目
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
