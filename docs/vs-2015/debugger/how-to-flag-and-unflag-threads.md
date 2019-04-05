---
title: '方法: フラグを設定し、スレッドのフラグ解除 |Microsoft Docs'
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
- treads, switching [debugging]
ms.assetid: 952d579d-6911-413e-b3e5-54e7e797e70c
caps.latest.revision: 36
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: be6ebe9e2031b24442f368b626d53b15a043023c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58962685"
---
# <a name="how-to-flag-and-unflag-threads"></a>方法: スレッドに対するフラグの設定と設定解除を行う
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

アイコンでマークすることによって、特に注目するスレッドのフラグを設定することができます、**スレッド**、**並列スタック**、**並列ウォッチ**、および**GPUスレッド**windows。 このアイコンにより、フラグが設定されているスレッドをそれ以外のスレッドと簡単に区別できるようになります。  
  
 フラグが設定されたスレッドは、特別な扱いも受信、**スレッド**ボックスの一覧、**デバッグの場所**ツールバー。 この一覧では、すべてのスレッドを表示することも、フラグが設定されたスレッドのみを表示することもできます。 スレッドのフラグを設定するときに、**スレッド**フラグが設定されたスレッドのみを表示するリストが自動的に切り替わりますが、切り替えることができます必要に応じてすべてのスレッドを表示します。  
  
### <a name="to-flag-or-unflag-a-thread-by-using-the-threads-window"></a>[スレッド] ウィンドウでスレッドに対するフラグを設定または解除するには  
  
-   **スレッド**ウィンドウで、興味のあるスレッドを検索し、選択するか、フラグをクリアするには、フラグ アイコンをクリックしています。  
  
### <a name="to-unflag-all-threads"></a>すべてのスレッドのフラグを解除するには  
  
-   **[スレッド]** ウィンドウで、いずれかのスレッドを右クリックし、**[すべてのスレッドのフラグを解除]** をクリックします。  
  
### <a name="to-display-only-flagged-threads"></a>フラグが設定されたスレッドのみ表示するには  
  
-   デバッグ ウィンドウでフラグ ボタンをクリックします。  
  
### <a name="to-flag-just-my-code"></a>マイ コードのみにフラグを設定するには  
  
1.  **[スレッド]** ウィンドウの上部にあるツール バーで、フラグ アイコンをクリックします。  
  
2.  ドロップダウン リストで、**[マイ コードのみにフラグを設定]** をクリックします。  
  
### <a name="to-flag-threads-that-are-associated-with-selected-modules"></a>選択したモジュールに関連するスレッドにフラグを設定するには  
  
1.  **[スレッド]** ウィンドウのツール バーで、フラグ アイコンをクリックします。  
  
2.  ドロップダウン リストで、**[カスタム モジュール選択にフラグを設定]** をクリックします。  
  
3.  **[モジュールの選択]** ダイアログ ボックスで、目的のモジュールを選択します。  
  
4.  (省略可能) **[検索]** ボックスに、特定のモジュールを検索するための文字列を入力します。  
  
5.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>関連項目  
 [マルチスレッド アプリケーションのデバッグ](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [チュートリアル: マルチスレッド アプリケーションのデバッグ](../debugger/walkthrough-debugging-a-multithreaded-application.md)
