---
title: エラー :別のユーザーとして、Microsoft Visual Studio リモート デバッグ モニター、リモート コンピューターでが実行されている |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- -anyuser option
- anyuser option
- Remote Debugging Monitor
- remote debugging, Remote Debugging Monitor
- msvsmon.exe
ms.assetid: e5b18734-2daf-4c58-b5de-24ae1295703e
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7cba3de8aa07a021d61e1ebb2a2c97f568eaf9ee
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63388433"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user"></a>エラー :リモート コンピューター上の Microsoft Visual Studio リモート デバッグ モニターは、別のユーザーで実行しています。
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

リモート デバッグを行おうとすると、次のエラー メッセージが表示される場合があります。  
  
 リモート コンピューター上の Microsoft Visual Studio リモート デバッグ モニターは、別のユーザーで実行しています。  
  
## <a name="cause"></a>原因  
 このメッセージは、認証なしモードでのデバッグ中に、msvsmon を起動したユーザーが Visual Studio を実行中のユーザーと一致しない場合に発生します。  
  
## <a name="solution"></a>ソリューション  
 最も安全で適切な解決策は、Visual Studio と同じユーザー アカウントでリモート デバッグ モニター (msvsmon.exe) を実行することです。 これができない場合は、リモート デバッグ モニターの **[オプション]** ダイアログ ボックスの **[すべてのユーザーにデバッグを許可する]** をオンにして他のアカウントでリモート デバッグ モニターを実行します。  
  
> [!CAUTION]
> 他のユーザーに接続する許可を与えると、誤ったリモート デバッグ セッションに接続してしまう可能性があります。 **認証なし**モードでのデバッグは決して安全ではなく、使用には注意が必要です。  
  
 詳細については、次を参照してください。[リモート デバッグ モニターを起動](http://msdn.microsoft.com/library/55b60ce7-834b-4e83-a10e-fe4248260a4c)します。  
  
## <a name="see-also"></a>関連項目  
 [リモート デバッグ エラーとトラブルシューティング](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)
