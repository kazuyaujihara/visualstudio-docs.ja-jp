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
ms.openlocfilehash: 1ee680a3d00c6736549b03ce8fee5593a7a8c5af
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575903"
---
# <a name="iactivescriptsitewindow"></a>IActiveScriptSiteWindow
このインターフェイスは、 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)と同じオブジェクトのユーザーインターフェイスをサポートするホストによって実装されます。 サーバーなどのユーザーインターフェイスをサポートしていないホストは、`IActiveScriptSiteWindow` インターフェイスを実装しません。 スクリプトエンジンは、`IActiveScriptSite` から `QueryInterface` を呼び出すことによって、このインターフェイスにアクセスします。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptSiteWindow::GetWindow](../../winscript/reference/iactivescriptsitewindow-getwindow.md)|スクリプトエンジンに表示する必要があるポップアップウィンドウの所有者として機能できるウィンドウハンドルを取得します。|  
|[IActiveScriptSiteWindow::EnableModeless](../../winscript/reference/iactivescriptsitewindow-enablemodeless.md)|ホストがメインウィンドウとモードレスダイアログボックスを有効または無効にします。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト インターフェイス](../../winscript/reference/active-script-interfaces.md)