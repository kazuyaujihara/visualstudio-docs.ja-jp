---
title: WriteAllTLogs |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- WriteAllTLogs
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- WriteAllTLogs
ms.assetid: 1fa3e10b-263c-4960-a9ad-485c02a7a872
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ee3f02be5494f85c0fa36be510f0a0c25caf53b6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62778444"
---
# <a name="writealltlogs"></a>WriteAllTLogs
すべてのスレッドとコンテキストの追跡ログを書き込みます。

## <a name="syntax"></a>構文

```cpp
HRESULT WINAPI WriteAllTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);
```

#### <a name="parameters"></a>パラメーター
[入力] `intermediateDirectory`

 追跡ログを格納するディレクトリ。

[入力] `tlogRootName`

 ログ ファイル名のルート名。

## <a name="return-value"></a>戻り値
 追跡コンテキストが作成された場合、**HRESULT** に **SUCCEEDED** ビットが設定されます。

## <a name="requirements"></a>要件
 **ヘッダー:***FileTracker.h*

## <a name="see-also"></a>関連項目
- [WriteContextTLogs](../msbuild/writecontexttlogs.md)