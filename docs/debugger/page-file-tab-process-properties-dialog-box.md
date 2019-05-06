---
title: ページファイル タブの プロセス プロパティ ダイアログ ボックス |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Process properties for Windows NT
ms.assetid: daf41a06-8a55-48f6-95f5-49a8416bd308
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 25dc3b0aca1b58c18ae4038540c14fc4dbfe4036
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62904108"
---
# <a name="page-file-tab-process-properties-dialog-box"></a>[ページ ファイル] タブ ([プロセス プロパティ] ダイアログ ボックス)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

使用して、**ページファイル**タブ プロセスのページング ファイルを確認します。 表示する、[プロセス プロパティ ダイアログ ボックス](../debugger/process-properties-dialog-box.md)、フォーカスを移動、[プロセス ビュー](../debugger/processes-view.md)ウィンドウ。 ツリーで、プロセスの任意のノードを選択し、**プロパティ**から、**ビュー**メニュー。  
  
 次の設定は [使用可能な**ページファイル**] タブ。  
  
|入力|説明|  
|-----------|-----------------|  
|**ページ ファイル サイズ**|ページング ファイル内でこのプロセスを使用しているページの現在数。 ページング ファイルには、ページのプロセスによって使用されますが、その他のファイルに含まれていないデータが格納されます。 ページング ファイルはすべてのプロセスによって使用され、ページング ファイル内の領域が不足している他のプロセスが実行中にエラーが発生します。|  
|**ピーク ページ ファイルのサイズ**|ページング ファイル内でこのプロセスが使用されるページの最大数。|  
|**ページ フォールト**|このプロセスで実行するスレッドによるページ フォールトの数。 ページ フォールトでは、スレッドがその作業をメイン メモリに設定されていない仮想メモリ ページを参照するときに発生します。 したがって、ページは取得されませんディスクからスタンバイ リスト上にある場合ため、メイン メモリ上に既にをもう 1 つ使用されているかどうか、またはのページを共有して処理します。|
