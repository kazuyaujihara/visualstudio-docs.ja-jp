---
title: SetThreadCount | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
apiname:
- SetThreadCount
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SetThreadCount
ms.assetid: 335335a5-8ca0-4e18-95f5-62aa6a691386
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 656e491e683c7ec2de23ea7e49938e833af3a295
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62945735"
---
# <a name="setthreadcount"></a>SetThreadCount
グローバルなスレッド カウントを設定し、そのカウントを現在のスレッドに割り当てます。

## <a name="syntax"></a>構文

```cmd
HRESULT WINAPI SetThreadCount(int threadCount);
```

#### <a name="parameters"></a>パラメーター
[入力] `threadCount`

 使用するスレッドの数。

## <a name="return-value"></a>戻り値
 スレッド カウントが更新された場合、**HRESULT** に **SUCCEEDED** ビットが設定されます。

## <a name="requirements"></a>要件
 **ヘッダー:**  *FileTracker.h*