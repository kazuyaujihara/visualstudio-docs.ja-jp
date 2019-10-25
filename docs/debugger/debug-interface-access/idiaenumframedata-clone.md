---
title: 'IDiaEnumFrameData:: Clone |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::Clone Method
ms.assetid: 28a17300-1626-422f-a17a-3a4d3872c37c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 47f6119eac1d48a7819f67bc57660c53e6b93b54
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744659"
---
# <a name="idiaenumframedataclone"></a>IDiaEnumFrameData::Clone
現在の列挙子と同じ列挙状態を含む列挙子を作成します。

## <a name="syntax"></a>構文

```C++
HRESULT Clone( 
   IDiaEnumFrameData** ppenum
);
```

#### <a name="parameters"></a>パラメーター
 ppenum

入出力列挙子の複製を含む[IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)オブジェクトを返します。 フレームデータは複製されず、列挙子だけがコピーされます。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)