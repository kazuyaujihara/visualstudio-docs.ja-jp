---
title: Sys (VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 294a6f9e-b49f-4c83-b322-5ac5411b66fb
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7968d35050c7b36957b56b9c707fe0404842a07a
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51749821"
---
# <a name="sys-vsperfcmd"></a>Sys (VSPerfCmd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

VSPerfCmd.exe の **Sys** オプションは、システム呼び出しイベント (プロファイリングされたアプリケーションからオペレーティング システムへの関数呼び出し) にサンプリングされるプロファイリング イベントを設定し、必要に応じて、サンプリング間隔のシステム呼び出し数を既定値の 10 から変更します。  
  
 **Sys** は、**Launch** オプションまたは **Attach** オプションも含むコマンド ラインでのみ使用できます。  
  
 既定では、プロファイラーのサンプリング イベントは、プロセッサのクロック サイクルに設定され、サンプリング間隔は 10,000,000 に設定されます。 **Timer**、**PF**、**Sys**、**Counter** の各オプションを使用すると、サンプリング イベントおよびサンプリング間隔を設定できます。 **GC** オプションは、割り当ておよびガベージ コレクション イベントが発生するたびに、.NET メモリ データを収集します。 コマンド ラインには、上記のオプションのいずれか 1 つだけを指定できます。  
  
 サンプリング イベントおよびサンプリング間隔は、**Launch** オプションまたは **Attach** オプションを含む最初のコマンド ラインでのみ設定できます。  
  
## <a name="syntax"></a>構文  
  
```  
VSPerfCmd.exe {/Launch:AppName|Attach:PID} /Sys[:Events] [Options]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Events`  
 サンプリング間隔におけるシステム呼び出しイベント数を指定する整数値。 ‎`Events` が指定されていない場合、間隔は 10 に設定されます。  
  
## <a name="required-options"></a>必須オプション  
 **Sys** には、次のオプションのいずれかが必要です。  
  
 **Launch:** `AppName`  
 プロファイラーと、`AppName` で指定されたアプリケーションを起動します。  
  
 **Attach:** `PID`  
 プロファイラーを `PID` で指定されたプロセスにアタッチします。  
  
## <a name="invalid-options"></a>無効なオプション  
 以下のオプションは、**Sys** と同じコマンド ラインには指定できません。  
  
 **PF**[**:**`Events`]  
 サンプリング イベントをページ フォールトに設定します。オプションで、サンプリング間隔を `Events` に設定します。 既定の PF 間隔は 10 です。  
  
 **Timer**[**:**`Cycles`]  
 サンプリング イベントをプロセッサのクロック サイクルに設定し、必要に応じてサンプリング間隔を `Cycles` に設定します。 既定の Timer 間隔は 10,000,000 です。  
  
 **Counter:** `Name`[`,Reload`[`,FriendlyName`]]  
 サンプリング イベントを、`Name` で指定された CPU パフォーマンス カウンターに設定し、サプリング間隔を `Reload` に設定します。  
  
 **GC**[**:**{**Allocation**&#124;**Lifetime**}]  
 .NET メモリ データを収集します。 既定 (**Allocation**) では、データはメモリの割り当てイベントごとに収集されます。 **Lifetime** パラメーターが指定されている場合、ガベージ コレクション イベントごとのデータも収集されます。  
  
## <a name="example"></a>例  
 この例では、プロファイラーのサンプリング イベントをシステム呼び出しに設定し、サンプリング間隔をサンプルごとに 20 の呼び出しに設定する方法を示します。  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Sys:20  
```  
  
## <a name="see-also"></a>関連項目  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [スタンドアロン アプリケーションのプロファイリング](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web アプリケーションのプロファイリング](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [プロファイリング (サービスの)](../profiling/command-line-profiling-of-services.md)



