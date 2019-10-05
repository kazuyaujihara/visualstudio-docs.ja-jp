---
title: WaitStart | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a409a4fe4ffe843df536e3c9e17a3a5a3b6560db
ms.sourcegitcommit: 4d2620bee4688fb881e09a07ea4a264b99f0743e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71322493"
---
# <a name="waitstart"></a>WaitStart
WaitStart オプションを指定すると、プロファイラーの初期化が完了したか、または指定した秒数が経過したときにのみ、*VSPerfCmd.exe* Start サブコマンドは制御を返します。 既定では、Start コマンドはすぐに制御を返します。 Start サブコマンドがプロファイラーを初期化せずに制御を返した場合、エラーが返されます。 秒数が指定されていない場合、Start コマンドは無期限に待機します。

 WaitStart オプションは、バッチ ファイルで、確実にプロファイラーが初期化されるようにする場合に役立ちます。

## <a name="syntax"></a>構文

```cmd
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /WaitStart[:Seconds]
```

#### <a name="parameters"></a>parameters
 `Seconds` Start サブコマンドから制御が返されるまで待機する秒数。

## <a name="required-options"></a>必須オプション
 WaitStart オプションは、Start サブコマンドでのみ使用できます。

 **出力:** `filename` 出力ファイル名を指定します。

## <a name="remarks"></a>解説

## <a name="example"></a>例
 このバッチ ファイルの例では、Start コマンドは、プロファイラーが初期化されるまで 5 秒間待機します。

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WaitStart:5
if not %errorlevel% 0 goto :error_tag
VSPerfCmd.exe /Launch:TestApp.exe
goto :end
:error_tag
@echo Could not start Profiler!
@echo Error %errorlevel%
:end
```
