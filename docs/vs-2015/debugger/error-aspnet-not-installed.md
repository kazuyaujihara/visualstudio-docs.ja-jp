---
title: エラー :ASP.NET がインストールされていない |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.http_not_supported
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Web applications, errors
- debugger, Web application errors
- error messages, ASP.NET
- ASP.NET, installation error messages
ms.assetid: 6286dd3d-3e2b-4edd-959d-81e0ed45500b
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 31268b94ab632e598badcba3def387ef1fc2ba1d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58962323"
---
# <a name="error-aspnet-not-installed"></a>エラー :ASP.NET がインストールされていません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このエラーは、デバッグを実行しようとしているコンピューターに [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] が正しくインストールされていない場合に発生します。 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] がインストールされていないか、[!INCLUDE[vstecasp](../includes/vstecasp-md.md)] がインストールされてから IIS がインストールされた可能性があります。  
  
### <a name="to-reinstall-aspnet"></a>ASP.NET を再インストールするには  
  
1.  コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
    ```  
    \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
    ```  
  
     場所*バージョン*v1.0.370 など、コンピューターにインストールされている .NET Framework のバージョン番号を表します。 によってフレームワークのバージョンを確認することができます、`\WINDOWS\Microsoft.NET\Framework`ディレクトリ。  
  
    > [!NOTE]
    >  Windows Server 2003 の場合は、コントロール パネルの **[プログラムの追加と削除]** を使って [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] をインストールできます。  
  
## <a name="see-also"></a>関連項目  
 [Web アプリケーションのデバッグ: エラーとトラブルシューティング](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
