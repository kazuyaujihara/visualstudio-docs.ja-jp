---
title: リモート デバッグ ダイアログ ボックスのファイアウォールの構成 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.firewallconfiguration
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
helpviewer_keywords:
- Configure Firewall for Remote Debugging dialog box
- remote debugging, configuring firewalls
- firewalls, configuring for remote debugging
ms.assetid: 5dff3393-fdeb-4129-a2f6-31f653107a82
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 91b0d7ee490b4e081a264c41b4fe85de07cb637b
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63437806"
---
# <a name="configure-firewall-for-remote-debugging-dialog-box"></a>[リモート デバッグのファイアウォールの構成] ダイアログ ボックス
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このダイアログ ボックスは、Windows ファイアウォールによってデバッガーがネットワーク経由で情報を受信できないときに表示されます。 リモート デバッグを続行するには、デバッガーが情報を受信できるようにファイアウォールに穴を開ける必要があります。  
  
> [!CAUTION]
> ファイアウォールに穴を開けると、ファイアウォールによってセキュリティ上の脅威がブロックされなくなるため、コンピューターが脅威にさらされる可能性があります。 リモート デバッグのための穴を開けると、Visual Studio 2015 のポート 4020 と 4021 のブロックが解除されます。 その他のバージョンの Visual Studio では、他のポート番号を使用します。 詳細については、次を参照してください。 [Remote Debugger Port Assignments](../debugger/remote-debugger-port-assignments.md)します。 また、デバッガーが追加のポートを開くことができるようになります。 詳細については、次を参照してください。[リモート デバッグ用の Windows ファイアウォールを構成する](../debugger/configure-the-windows-firewall-for-remote-debugging.md)します。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **リモート デバッグを取り消す**  
 リモート デバッグをキャンセルします。 コンピューターのセキュリティ設定はそのままの状態で保持されます。  
  
 **ローカル ネットワーク (サブネット) 上のコンピューターからのリモート デバッグは制限しない**  
 ローカル サブネット上のコンピューターのリモート デバッグを有効にします。 これにより、ローカル サブネット上のコンピューターが脆弱になることがありますが、引き続きファイアウォールによってサブネットの外部から入ってくる情報がブロックされます。  
  
 **すべてのコンピューターからのリモート デバッグを制限しない**  
 ネットワーク上のすべての場所にあるコンピューターのリモート デバッグを有効にします。 この設定では、セキュリティが最も低くなります。  
  
## <a name="see-also"></a>関連項目  
 [デバッガーのセキュリティ](../debugger/debugger-security.md)   
 [デバイスのリモート ツールをセットアップします。](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)   
 [デバッグ用ユーザー インターフェイス リファレンス](../debugger/debugging-user-interface-reference.md)
