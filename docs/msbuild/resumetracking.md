---
title: ResumeTracking | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- ResumeTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- ResumeTracking
ms.assetid: d637e019-7c50-4b0a-812e-bc822001e697
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0e2ff32a4eb2218a8b3d09188c787156e484147f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62996690"
---
# <a name="resumetracking"></a>ResumeTracking
現在のコンテキストで追跡を再開します。

## <a name="syntax"></a>構文

```cpp
HRESULT WINAPI ResumeTracking();
```

## <a name="return-value"></a>戻り値
 追跡が再開された場合、**HRESULT** に **SUCCEEDED** ビットが設定されます。 コンテキストが利用できず、追跡を再開できない場合、**E_FAIL** が返されます。

## <a name="requirements"></a>要件
 **ヘッダー:**  *FileTracker.h*

## <a name="see-also"></a>関連項目
- [SuspendTracking](../msbuild/suspendtracking.md)