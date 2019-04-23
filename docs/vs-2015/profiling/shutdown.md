---
title: Shutdown | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: fbbbd27cfe7d720349592050419f5c73d1843c70
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60115407"
---
# <a name="shutdown"></a>シャットダウン
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**Shutdown** オプションは、現在プロファイル中のプロセスが終了するかデタッチされるまで待機して、プロファイラーをオフにし、プロファイル データ ファイルを閉じます。 **Shutdown** オプションは、プロファイル実行の最後のコマンドである必要があります。  
  
 タイムアウト パラメーターが指定されていない場合、**Shutdown** オプションは無期限に待機します。 タイムアウト パラメーターが指定されている場合、指定された秒数の経過後にオプションから制御が戻りますが、プロファイラーはオフにされず、データ ファイルも閉じられません。  
  
 コマンド ラインで指定するオプションは **Shutdown** オプションのみにする必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
VSPerfCmd.exe /Shutdown[:Timeout]  
```  
  
#### <a name="parameters"></a>パラメーター  
`Timeout`  
- (省略可能) 指定した場合は、指定した秒数の経過後にオプションから制御が戻りますが、プロファイラーはオフにされず、プロファイル データ ファイルも閉じられません。  
  
## <a name="see-also"></a>関連項目  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [スタンドアロン アプリケーションのプロファイリング](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web アプリケーションのプロファイリング](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [プロファイリング (サービスの)](../profiling/command-line-profiling-of-services.md)
