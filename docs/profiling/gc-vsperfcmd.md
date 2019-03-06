---
title: GC (VSPerfCmd) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7c81e88b-a748-4cf5-a7a1-3429608e1b54
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 50b2e269ec292aaf37b8d0c707fa27ff8268a1f0
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56596129"
---
# <a name="gc-vsperfcmd"></a>GC (VSPerfCmd)
**GC** オプションは、.NET Framework メモリ割り当てとオブジェクト有効期間データを収集できます。 **GC** オプションはサンプリング プロファイリング方法でのみ、かつ、**Launch** オプションとの併用でのみ利用できます。

 **GC** オプションを使用するとき、VSPerfClrEnv **/sampleon** コマンドは必要ありません。

 パラメーターが指定されていない場合、あるいは **Allocation** パラメーターが指定されている場合、.NET Framework メモリ割り当てデータのみが収集されます。 **Lifetime** パラメーターが指定されている場合、.NET Framework メモリ割り当てと .NET Framework オブジェクト有効期間データの両方が収集されます。

## <a name="syntax"></a>構文

```cmd
VSPerfCmd.exe /Launch:AppName /GC[:{Allocation|Lifetime}] [Options]
```

#### <a name="parameters"></a>パラメーター
 **Allocation** 既定値。 .NET Framework メモリ割り当てデータを収集します。

 **Lifetime** .NET Framework メモリ割り当てデータと .NET Framework オブジェクト有効期間データの両方を収集します。

## <a name="required-options"></a>必須オプション
 **GC** オプションは、**Launch** オプションと一緒に指定する場合にのみ使用できます。

 **Launch:**`AppName` 指定したアプリケーションを起動し、サンプリング メソッドでプロファイリングを開始します。

## <a name="example"></a>例
 次の例では、アプリケーションが起動し、.NET Framework メモリ割り当てデータが収集されます。

```cmd
VSPerfCmd.exe /Launch:TestApp.exe /gc
```

## <a name="see-also"></a>関連項目
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [スタンドアロン アプリケーションのプロファイリング](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [ASP.NET Web アプリケーションのプロファイリング](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [サービスのプロファイリング](../profiling/command-line-profiling-of-services.md)