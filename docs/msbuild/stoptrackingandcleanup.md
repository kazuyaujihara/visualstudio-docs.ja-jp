---
title: StopTrackingAndCleanup | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- StopTrackingAndCleanup
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- StopTrackingAndCleanup
ms.assetid: 9f8c5994-2dfc-43c3-a5fb-89b2f8990429
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 56f4fb82ab0e9792cadbeeea05499744e4c8ce46
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56621306"
---
# <a name="stoptrackingandcleanup"></a>StopTrackingAndCleanup
すべての追跡を停止し、追跡セッションで使用されているメモリを解放します。

## <a name="syntax"></a>構文

```cpp
HRESULT WINAPI StopTrackingAndCleanup(void);
```

## <a name="return-value"></a>戻り値
 追跡が停止された場合、**HRESULT** に **SUCCEEDED** ビットが設定され、返されます。

## <a name="requirements"></a>要件
 **ヘッダー:***FileTracker.h*

## <a name="see-also"></a>関連項目
- [StartTrackingContext](../msbuild/starttrackingcontext.md)