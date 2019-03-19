---
title: IActiveScriptSiteWindow |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSiteWindow interface
ms.assetid: 96d5c493-2c0b-47e2-848b-4a8dacdcd65c
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3691a874121c00dcccc69958eb5746a2c1d78122
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58149459"
---
# <a name="iactivescriptsitewindow"></a>IActiveScriptSiteWindow
このインターフェイスはホストと同じオブジェクトのユーザー インターフェイスをサポートする[IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)します。 実装しませんサーバーなどのユーザー インターフェイスをサポートしないホスト、`IActiveScriptSiteWindow`インターフェイス。 スクリプト エンジンが呼び出すことによってこのインターフェイスにアクセスする`QueryInterface`から`IActiveScriptSite`します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptSiteWindow::GetWindow](../../winscript/reference/iactivescriptsitewindow-getwindow.md)|スクリプト エンジンを表示する必要がある、ポップアップ ウィンドウの所有者として機能するウィンドウ ハンドルを取得します。|  
|[IActiveScriptSiteWindow::EnableModeless](../../winscript/reference/iactivescriptsitewindow-enablemodeless.md)|有効または無効のメイン ウィンドウと同様、モードレス ダイアログ ボックスにホストをによりします。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト インターフェイス](../../winscript/reference/active-script-interfaces.md)