---
title: '方法: ASP.NET の例外のデバッグ |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], ASP.NET exceptions
- ASP.NET, exceptions
- exceptions, ASP.NET
ms.assetid: 1810096e-de8c-435e-be3d-f365d0cd0a6a
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1ccd8c399bd92bd98307d44aff913c30390033c7
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60083713"
---
# <a name="how-to-debug-aspnet-exceptions"></a>方法: ASP.NET の例外をデバッグする
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

例外のデバッグは、堅牢な [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] アプリケーションの開発において重要な部分です。 例外をデバッグする方法についての全般については、「[デバッガーでの例外を管理する](../debugger/managing-exceptions-with-the-debugger.md)します。  
  
 ハンドルされない [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 例外をデバッグする場合、その例外でデバッガーが停止していることを確認する必要があります。 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] ランタイムにはトップレベルの例外ハンドラーがあります。 そのため、デバッガーは既定では、ハンドルされない例外で実行を中断することはありません。 例外がスローされたときに、デバッガーに割り込むを選択する必要があります**例外は、ときに中断します。スロー**でその特定の例外の設定、**例外** ダイアログ ボックス。  
  
 マイ コードのみを有効にした場合**例外は、ときに中断します。スロー**デバッガーが .NET Framework メソッドやその他のシステム コードで例外がスローされた場合、すぐに中断は発生しません。 デバッガーがシステム コード以外のコードをヒットするまで実行は継続され、ヒットした時点でデバッガーは中断されます。 つまり、例外が発生したときにシステム コードをステップ実行する必要はありません。  
  
 マイ コードのみでは、さらに便利なことができる別のオプションを示します。**例外は、するときに中断します。ユーザーよって処理されない**します。 例外にこの設定を選択すると、ユーザー コードで例外が取得され、処理された場合にのみ、デバッガーによってユーザー コードの実行が中断されます。 この設定では、トップレベルの [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 例外ハンドラーの効果が無視されます。この例外ハンドラーがユーザー コードではないためです。  
  
### <a name="to-enable-debugging-of-aspnet-exceptions-with-just-my-code"></a>[マイ コードのみ] で ASP.NET 例外を有効にするには  
  
1. **[デバッグ]** メニューの **[例外]** をクリックします。  
  
     **[例外]** ダイアログ ボックスが表示されます。  
  
2. **[Common Language Runtime Exceptions]** 行の **[スローされるとき]** または **[ユーザーにハンドルされていないとき]** チェック ボックスをオンにします。  
  
     **[ユーザーにハンドルされていないとき]** 設定を使用するには、**[マイ コードのみ]** を有効にする必要があります。  
  
### <a name="to-use-best-practices-for-aspnet-exception-handling"></a>ASP.NET の例外処理で推奨される手順を使用するには  
  
- 予測でき、処理方法がわかる例外をスローできるコードを、`try … catch` ブロックで囲みます。 たとえば場合は、アプリケーションは、XML Web サービスまたは SQL Server に直接呼び出しを行うは、そのコードがでなければなりません**try… catch**数多くの例外が発生する可能性があるためにをブロックします。
