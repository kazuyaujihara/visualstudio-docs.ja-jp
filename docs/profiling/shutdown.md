---
title: Shutdown | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 29f6ab4b750370467fa75c2341e20264db756a7f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62979888"
---
# <a name="shutdown"></a>シャットダウン
**Shutdown** オプションは、現在プロファイル中のプロセスが終了するかデタッチされるまで待機して、プロファイラーをオフにし、プロファイル データ ファイルを閉じます。 **Shutdown** オプションは、プロファイル実行の最後のコマンドである必要があります。

 タイムアウト パラメーターが指定されていない場合、**Shutdown** オプションは無期限に待機します。 タイムアウト パラメーターが指定されている場合、指定された秒数の経過後にオプションから制御が戻りますが、プロファイラーはオフにされず、データ ファイルも閉じられません。

 コマンド ラインで指定するオプションは **Shutdown** オプションのみにする必要があります。

## <a name="syntax"></a>構文

```cmd
VSPerfCmd.exe /Shutdown[:Timeout]
```

#### <a name="parameters"></a>パラメーター
`Timeout`
- (省略可能) 指定した場合は、指定した秒数の経過後にオプションから制御が戻りますが、プロファイラーはオフにされず、プロファイル データ ファイルも閉じられません。

## <a name="see-also"></a>関連項目
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [スタンドアロン アプリケーションのプロファイリング](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [ASP.NET Web アプリケーションのプロファイリング](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [サービスのプロファイリング](../profiling/command-line-profiling-of-services.md)