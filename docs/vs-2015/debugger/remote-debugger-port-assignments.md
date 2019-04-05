---
title: リモート デバッガーのポートの割り当て |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 238bb4ec-bb00-4c2b-986e-18ac278f3959
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c1e70ec3ba50e5be1ed532bb4a88cbdd500af09c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973464"
---
# <a name="remote-debugger-port-assignments"></a>リモート デバッガーのポートの割り当て
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio リモート デバッガーは、アプリケーションまたはバック グラウンド サービスとして実行できます。 アプリケーションとして実行される際には、次のように既定で割り当てられているポートを使用します。  
  
- Visual Studio 2015:4020  
  
- Visual Studio 2013:4018  
  
- Visual Studio 2012:4016  
  
  つまり、リモート デバッガーに割り当てられるポート番号はリリースごとに 2 つずつ増えます。 別の任意のポート番号を設定することができます。 ポート番号の設定方法は、後のセクションで説明します。  
  
## <a name="the-remote-debugger-port-on-32-bit-operating-systems"></a>32 ビット オペレーティング システムのリモート デバッガーのポート  
 TCP 4020 (Visual Studio 2015 の場合) がメイン ポートであり、すべてのシナリオにこれが必要です。 これは、コマンド ラインまたはリモート デバッガー ウィンドウのいずれかから構成できます。  
  
 リモート デバッガー ウィンドウでは、 **[ツール] / [オプション]** の順にクリックし、TCP/IP ポート番号を設定します。  
  
 コマンド ラインでは、**/port** スイッチを使用して「**msvsmon /port \<ポート番号>**」と入力して、リモート デバッガーを開始します。  
  
 リモート デバッグのヘルプに、リモート デバッガーのすべてのコマンド ライン スイッチが記載されています (リモート デバッガー ウィンドウで **F1** キーを押すか、または **[ヘルプ] / [使い方]** の順にクリックします)。  
  
## <a name="the-remote-debugger-port-on-64-bit-operating-systems"></a>64 ビット オペレーティング システムのリモート デバッガーのポート  
 64 ビット バージョンのリモート デバッガーを開始すると、既定でポート 4020 が使用されます。  32 ビット プロセスをデバッグする場合は、64 ビット バージョンのリモート デバッガーにより、ポート 4021 で 32 ビット バージョンのリモート デバッガーが開始されます。 32 ビットのリモート デバッガーを実行する場合は、4020 が使用され、4021 は使用されません。  
  
 このポートは、コマンドラインから構成できます。**Msvsmon/wow64port\<ポート番号 >** します。  
  
## <a name="the-discovery-port"></a>検出ポート  
 実行中のリモート デバッガーのインスタンスをネットワークで検出するには (たとえば、 **[プロセスにアタッチ]** ダイアログの **[検索]** ダイアログ)、UDP 3702 が使用されます。 これが使用されるのは、リモート デバッガーを実行しているコンピューターを検出する場合だけです。つまり、ターゲット コンピューターのコンピューター名または IP アドレスが他の方法でわかれば省略できます。 これは検出用の標準ポートなので、ポート番号を構成することはできません。  
  
 探索を有効にしたくない場合は、検出を無効にコマンドラインから msvsmon を開始できます。**Msvsmon/nodiscovery**します。  
  
## <a name="remote-debugger-ports-on-azure"></a>Azure でのリモート デバッガーのポート  
 Azure のリモート デバッガーでは次のポートが使用されます。 クラウド サービス上のポートは、個々の VM 上のポートにマップされます。 すべてのポートは TCP です。  
  
||||  
|-|-|-|  
|**接続**|**クラウド サービス上のポート**|**VM 上のポート**|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Connector|30400|30398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Forwarder|31400|31398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.FileUpload|32400|32398|  
  
## <a name="see-also"></a>関連項目  
 [Remote Debugging](../debugger/remote-debugging.md)
