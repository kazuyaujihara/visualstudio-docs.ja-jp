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
ms.openlocfilehash: 67e16e2825f03c9ae452e639d6a086bee584ac95
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58152643"
---
# <a name="iactivescriptsite"></a>IActiveScriptSite
Windows スクリプト エンジンのサイトを作成するホストによって実装されます。 通常、このサイトは、スクリプト (たとえば、ActiveX コントロール) に表示されるすべてのオブジェクトのコンテナーに関連付けられます。 通常、このコンテナーは、ドキュメントまたは表示されているページに対応します。 たとえば、Microsoft Internet Explorer は、HTML ページが表示されている各のようなコンテナーを作成は。 各 ActiveX コントロール (またはその他のオートメーション オブジェクト)、ページと、スクリプト エンジン自体には、このコンテナー内で列挙可能になります。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|||  
|-|-|  
|メソッド|説明|  
|[IActiveScriptSite::GetLCID](../../winscript/reference/iactivescriptsite-getlcid.md)|ユーザー インターフェイス要素を表示するため、ホストを使用するロケール識別子を取得します。|  
|[IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md)|呼び出すことによって、エンジンに追加された項目に関する情報を取得、 [iactivescript::addnameditem](../../winscript/reference/iactivescript-addnameditem.md)メソッド。|  
|[IActiveScriptSite::GetDocVersionString](../../winscript/reference/iactivescriptsite-getdocversionstring.md)|ホストの観点から現在のドキュメントのバージョンを一意に識別するホスト定義の文字列を取得します。|  
|[IActiveScriptSite::OnScriptTerminate](../../winscript/reference/iactivescriptsite-onscriptterminate.md)|スクリプトの実行が完了したときに呼び出されます。|  
|[IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md)|スクリプト エンジンの状態が変更されたことをホストに通知します。|  
|[IActiveScriptSite::OnScriptError](../../winscript/reference/iactivescriptsite-onscripterror.md)|エンジンが、スクリプトの実行中に、実行エラーが発生したことをホストに通知します。|  
|[IActiveScriptSite::OnEnterScript](../../winscript/reference/iactivescriptsite-onenterscript.md)|スクリプト エンジンのスクリプト コードの実行が開始されたことをホストに通知します。|  
|[IActiveScriptSite::OnLeaveScript](../../winscript/reference/iactivescriptsite-onleavescript.md)|スクリプト コードを実行してから、スクリプト エンジンが返されることをホストに通知します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト インターフェイス](../../winscript/reference/active-script-interfaces.md)