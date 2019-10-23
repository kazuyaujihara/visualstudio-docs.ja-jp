---
title: 'IDiaFrameData:: get_program |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_program method
ms.assetid: 9201409e-b4b1-4e2e-a9f8-d17678ac538b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 135f2b0a042dd74b573a0746831a48fb27e7c2a9
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743520"
---
# <a name="idiaframedataget_program"></a>IDiaFrameData::get_program
現在の関数の呼び出しの前にレジスタセットを計算するために使用されるプログラム文字列を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_program ( 
   BSTR* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力プログラム文字列を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 プログラム文字列は、プロローグを確立するために解釈されるマクロのシーケンスです。 たとえば、一般的なスタックフレームでは、プログラム文字列 `"$T0 $ebp = $eip $T0 4 + ^ = $ebp $T0 ^ = $esp $T0 8 + ="` を使用する場合があります。 形式は、逆ポーランド表記で、演算子はオペランドに従います。 `T0` は、スタック上の一時変数を表します。 この例では、次の手順を実行します。

1. Register `ebp` の内容を `T0` に移動します。

2. アドレスを生成し、そのアドレスから値を取得して、値をレジスタ `eip` に格納するには、`T0` の値に `4` を追加します。

3. @No__t_0 に格納されているアドレスから値を取得し、その値を register `ebp` に格納します。

4. @No__t_1 の値に `8` を追加し、その値を register `esp` に格納します。

   プログラム文字列は CPU と、現在のスタックフレームによって表される関数に設定されている呼び出し規約に固有であることに注意してください。

## <a name="see-also"></a>関連項目
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)