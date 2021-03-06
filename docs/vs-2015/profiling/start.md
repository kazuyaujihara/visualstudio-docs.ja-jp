---
title: Start | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b85d0fe9-f67a-4b7c-8d48-7eecf3f2dfe9
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6c2f52a000cdf5eaa1a1ef4b9afeb141500f1911
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51724178"
---
# <a name="start"></a>[開始]
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**Start** オプションは、指定されたプロファイリング方法にプロファイラーを初期化する VSPerfCmd.exe オプションです。  
  
## <a name="syntax"></a>構文  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName [Options]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Method`  
 次のいずれかのキーワードを指定する必要があります。  
  
-   **TRACE** - インストルメンテーション メソッドを指定します。  
  
-   **SAMPLE** - サンプリング方法を指定します。  
  
-   **COVERAGE** - コード カバレッジを指定します。  
  
-   **CONCURRENCY** - リソースの競合メソッドを指定します。  
  
## <a name="required-options"></a>必須オプション  
 **Output** オプションは、コマンド ラインで **Start** が指定されている場合に指定する必要があります。  
  
 **Output:** `filename`  
 出力ファイル名を指定します。  
  
## <a name="exclusive-options"></a>排他的なオプション  
 次のオプションは、コマンド ラインで **Start** とともにのみ使用できます。  
  
 **CrossSession**&#124;**CS**  
 プロセス間のプロファイリングを有効にします。 オプション名 **CrossSession** と **CS** は両方ともサポートされています。  
  
 **User:**[`domain\`]`username`  
 指定されたアカウントからモニターへのクライアント アクセスを有効にします。  
  
 **WinCounter:** `Path` [**Automark**:`n`]  
 **WinCounter** は、プロファイリング データ ファイル内にマークとして含める Windows パフォーマンス カウンターを指定します。 **AutoMark** は、データ ファイルのコレクション間の間隔をミリ秒単位で指定します。  
  
## <a name="invalid-options"></a>無効なオプション  
 次のオプションは、コマンド ラインで **Start** オプションとともに使用することができません。  
  
 **Status**  
 **Status** は、プロファイリングされるプロセスに適用されます。 プロセスとスレッドが現在のプロファイル状態 (オン/オフ) とともに一覧表示されます。 たとえば、プロセスが停止されても、**Status** はこのプロセスをレポートに記録しません。 **Status** は、プロセスがプロファイリングされているかどうかを示します。  
  
 **Shutdown**[**:**`Timeout`]  
 プロファイラーをオフにします。  
  
## <a name="example"></a>例  
 次の例では、VSPerfCmd.exe の **Start** オプションを使用してプロファイラーを初期化する方法を示します。  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>関連項目  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [スタンドアロン アプリケーションのプロファイリング](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web アプリケーションのプロファイリング](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [プロファイリング (サービスの)](../profiling/command-line-profiling-of-services.md)



