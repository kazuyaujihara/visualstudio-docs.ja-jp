---
title: IActiveScriptSite |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSite interface
ms.assetid: 4d604a11-5365-46cf-ab71-39b3dbbe9f22
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 56b2a749eb3553044bda5816639498a0682e37e0
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72570087"
---
# <a name="iactivescriptsite"></a>IActiveScriptSite
Windows スクリプトエンジン用のサイトを作成するために、ホストによって実装されます。 通常、このサイトは、スクリプトに表示されるすべてのオブジェクト (ActiveX コントロールなど) のコンテナーに関連付けられます。 通常、このコンテナーは、表示されているドキュメントまたはページに対応します。 たとえば、Microsoft Internet Explorer では、表示される HTML ページごとにこのようなコンテナーが作成されます。 このコンテナー内では、ページ上の各 ActiveX コントロール (またはその他のオートメーションオブジェクト) とスクリプトエンジン自体が列挙可能です。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|||  
|-|-|  
|メソッド|説明|  
|[IActiveScriptSite::GetLCID](../../winscript/reference/iactivescriptsite-getlcid.md)|ホストがユーザーインターフェイス要素を表示するために使用するロケール識別子を取得します。|  
|[IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md)|[IActiveScript:: AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md)メソッドの呼び出しによってエンジンに追加された項目に関する情報を取得します。|  
|[IActiveScriptSite::GetDocVersionString](../../winscript/reference/iactivescriptsite-getdocversionstring.md)|ホストの観点から、現在のドキュメントのバージョンを一意に識別するホスト定義の文字列を取得します。|  
|[IActiveScriptSite::OnScriptTerminate](../../winscript/reference/iactivescriptsite-onscriptterminate.md)|スクリプトの実行が完了すると呼び出されます。|  
|[IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md)|スクリプトエンジンによって状態が変更されたことをホストに通知します。|  
|[IActiveScriptSite::OnScriptError](../../winscript/reference/iactivescriptsite-onscripterror.md)|エンジンがスクリプトを実行している間に実行エラーが発生したことをホストに通知します。|  
|[IActiveScriptSite::OnEnterScript](../../winscript/reference/iactivescriptsite-onenterscript.md)|スクリプトエンジンがスクリプトコードの実行を開始したことをホストに通知します。|  
|[IActiveScriptSite::OnLeaveScript](../../winscript/reference/iactivescriptsite-onleavescript.md)|スクリプトエンジンがスクリプトコードの実行から返されたことをホストに通知します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト インターフェイス](../../winscript/reference/active-script-interfaces.md)