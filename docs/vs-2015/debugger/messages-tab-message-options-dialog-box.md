---
title: '[メッセージ] タブ、[メッセージ オプション] ダイアログ ボックス |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- message options, Messages
ms.assetid: fb9fa211-e82c-40a5-9e4b-ba8de07313c0
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a9eb1c88d935fa307e8b86a9a75da423bc08111c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58963697"
---
# <a name="messages-tab-message-options-dialog-box"></a>[メッセージ] タブ ([メッセージ オプション] ダイアログ ボックス)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

使用して、**メッセージ**リストにするメッセージの種類を選択するタブ[メッセージ ビュー](../debugger/messages-view.md)メッセージの検索条件を指定するとします。 表示する、[メッセージ オプション ダイアログ ボックス](../debugger/message-options-dialog-box.md)、選択**ログ メッセージ**から、**スパイ**メニュー。  
  
 選択した一般に、**メッセージ グループ**、個々 に選択して、選択範囲を調整および**ビューへのメッセージ**します。 **すべて**ボタンは、すべてのメッセージの種類を選択、 **None**ボタンは、すべての種類をクリアします。  
  
 次の設定は [使用可能な**メッセージ**] タブ。  
  
 **表示するメッセージ**  
 表示するための特定のメッセージを選択します。 新しいメッセージ ウィンドウを作成するときに、すべてのメッセージを表示できます。 メッセージをフィルター処理する場合、**メッセージ** タブで、そのフィルターはのみ Windows ビューで表示されているメッセージいない、新しいメッセージに適用されます。  
  
 **メッセージ グループ**  
 表示するメッセージのグループを選択します。 使用可能なグループは次のとおりです。  
  
- WM_USER 以上のコードで WM_USER:  
  
- 登録: 登録されている、**を通じて**を呼び出す  
  
- 0 (WM_USER – 1) の範囲内の不明: 不明なメッセージ  
  
  なおこれら**メッセージ グループ**で特定のエントリにマップされていない**表示するメッセージ**します。 グループを選択すると、選択範囲は、メッセージ ストリームに直接適用されます。  
  
  内で灰色表示のチェック ボックス**メッセージ グループ**ことを示します、**表示するメッセージ**そのグループ内のメッセージ ボックスの一覧が変更されました。 そのグループ内のメッセージの種類のすべてが選択されています。  
  
  **設定を既定値として保存**  
  メッセージの検索オプションとしては、後で使用できるは、現在の設定を保存します。 これらの設定は、spy++ を終了するときにも保存されます。
