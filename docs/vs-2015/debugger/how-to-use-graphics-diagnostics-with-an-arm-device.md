---
title: '方法: ARM デバイスでグラフィックス診断を使用して |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 346fd3c0-9e92-4ab8-bb3b-1aa9000a2483
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7ae934de4a9f0dbcf4076d7402abd138eac20268
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60104877"
---
# <a name="how-to-use-graphics-diagnostics-with-an-arm-device"></a>方法: ARM デバイスでグラフィックス診断を使用してください。
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

グラフィックス診断は、Windows RT 8.1 または Windows Phone 8.1 を実行する ARM ベースのデバイスで Direct3D アプリケーションのリモート デバッグをサポートします。 Direct3D がデバイス上で実行されている間に、Direct3D アプリケーショングラフィックス情報をキャプチャできます。また以前にキャプチャしたグラフィックス情報については、デバイスを再生コンピューターとして使用できます。  
  
## <a name="using-graphics-diagnostics-with-an-arm-based-device"></a>ARM ベースのデバイスでのグラフィックス診断の使用  
 Visual Studio は ARM ベースのデバイス上では稼動しないため、これらのデバイス上で稼動するアプリケーションを分析するにはリモート デバッガーを使用する必要があります。 リモート デバッガーはグラフィックスのキャプチャと再生をサポートしているため、アプリケーションをデバッグするのと同じくらい簡単に、レンダリングのエラーを診断し、これらのデバイスのグラフィックス パフォーマンスを評価することができます。  
  
 グラフィックス診断の機能を使用するには、最初にデバイス上でリモート デバッギングを有効にします。  
  
#### <a name="to-enable-remote-debugging-on-your-arm-based-device"></a>ARM ベースのデバイス上でリモート デバッギングを有効にするには  
  
1. インストール、 [ARM Kits Policy](http://msdn.microsoft.com/windows/desktop/dn469188) ARM ベースのデバイスにします。  
  
2. インストール、 [Remote Debugging Tools](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015) ARM ベースのデバイスにします。  
  
> [!IMPORTANT]
>  Windows Phone 8.1 のデバイスの場合は、開発用にスマートフォンを登録しなければならないことがあります。 そのためには、自身が登録されている開発者であることが必要です。 詳細については、次を参照してください。[展開および Windows Phone 8 向けアプリを実行する方法](http://msdn.microsoft.com/library/windowsphone/develop/ff402565.aspx)します。  
  
 デバイス上でリモート デバッギングを有効にしたら、デバイスをデバッグ ターゲットにしてグラフィックス診断を開始します。  
  
#### <a name="to-configure-and-start-graphics-diagnostics-on-your-device"></a>デバイス上でグラフィックス診断を構成および開始するには  
  
1. **ソリューション プラットフォーム**ドロップダウン リストで、 **ARM** ARM ベースのデバイスをリモート デバッグ ターゲットとして使用できるようにします。  
  
2. **デバッグ ターゲット**ドロップダウン リストで、ARM デバイスを選択します。  
  
3. メニューで、次のように選択します。**デバッグ**、**グラフィックス**、**診断の開始**します。 (キーボード:Alt キーを押しながら f5 キー)  
  
## <a name="see-also"></a>関連項目  
 [リモート コンピューター上の Windows ストア アプリを実行します。](../debugger/run-windows-store-apps-on-a-remote-machine.md)   
 [方法: グラフィックス診断再生マシンを変更する](../debugger/how-to-change-the-graphics-diagnostics-playback-machine.md)
