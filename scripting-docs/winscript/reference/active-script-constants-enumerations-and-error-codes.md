---
title: アクティブスクリプトの定数、列挙型、およびエラーコード |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: aab24471-5817-45c0-be07-ffe4648923ed
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e03bef99c2297d517aa5234db49820a2b9600ce7
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572709"
---
# <a name="active-script-constants-enumerations-and-error-codes"></a>アクティブ スクリプトの定数、列挙型、およびエラー コード
このセクションでは、Windows スクリプトエンジンで使用される列挙型とエラーコードについて説明します。  
  
## <a name="constants"></a>定数  
  
|定数|説明|  
|--------------|-----------------|  
|[SCRIPTTHREADID 定数](../../winscript/reference/scriptthreadid-constants.md)|スレッドの種類を指定します。|  
  
## <a name="properties"></a>プロパティ  
  
|property|説明|  
|--------------|-----------------|  
|[SCRIPTPROP_HOSTKEEPALIVE プロパティ](../../winscript/reference/scriptprop-hostkeepalive-property.md)|未解決の参照がある場合に、スクリプトエンジンを完全に機能させるかどうかを指定するために使用します。|  
  
## <a name="enumerations"></a>列挙  
  
|列挙|説明|  
|-----------------|-----------------|  
|[SCRIPTGCTYPE 列挙型](../../winscript/reference/scriptgctype-enumeration.md)|実行するガベージコレクションの型。|  
|[SCRIPTLANGUAGEVERSION 列挙型](../../winscript/reference/scriptlanguageversion-enumeration.md)|有効なスクリプトバージョンを指定します。|  
|[SCRIPTSTATE 列挙型](../../winscript/reference/scriptstate-enumeration.md)|スクリプトエンジンの状態を指定します。|  
|||  
|[SCRIPTTHREADSTATE 列挙型](../../winscript/reference/scriptthreadstate-enumeration.md)|スクリプトエンジンのスレッドの状態を指定します。|  
|[SCRIPTTRACEINFO 列挙型](../../winscript/reference/scripttraceinfo-enumeration.md)|トレースされているスクリプトイベントを表します。 [IActiveScriptSiteTraceInfo:: SendScriptTraceInfo メソッド](../../winscript/reference/iactivescriptsitetraceinfo-sendscripttraceinfo-method.md)で使用されます。|  
|[SCRIPTUICHANDLING 列挙型](../../winscript/reference/scriptuichandling-enumeration.md)|UI コントロールを処理する方法を表します。|  
|[SCRIPTUICITEM 列挙型](../../winscript/reference/scriptuicitem-enumeration.md)|UI 項目の種類を表します。 [IActiveScriptSiteUIControl:: GetUIBehavior メソッド](../../winscript/reference/iactivescriptsiteuicontrol-getuibehavior-method.md)で使用されます。|  
  
## <a name="error-codes"></a>エラー コード  
  
|エラー コード|説明|  
|----------------|-----------------|  
|[SCRIPT_E_PROPAGATE エラー コード](../../winscript/reference/script-e-propagate-error-code.md)|スクリプトエラーが呼び出し元に伝達されています。これは別のスレッドに存在する可能性があります。|  
|[SCRIPT_E_RECORDED エラー コード](../../winscript/reference/script-e-recorded-error-code.md)|スクリプトエンジンとホストの間でエラーが発生しました。|  
|[SCRIPT_E_REPORTED エラー コード](../../winscript/reference/script-e-reported-error-code.md)|スクリプトエンジンがホストに対してハンドルされない例外を報告しました。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト インターフェイス](../../winscript/reference/active-script-interfaces.md)