---
title: IActiveScriptProfilerCallback2 インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptProfilerCallback2 interface
ms.assetid: 8f2e62e4-c232-4dc3-a2c0-54dd06298306
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d95c3db11551eb6551f509b4afbe52a70ff55ab9
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58145735"
---
# <a name="iactivescriptprofilercallback2-interface"></a>IActiveScriptProfilerCallback2 インターフェイス
ドキュメント オブジェクト モデル (DOM) のイベントが発生したときにプロファイラー オブジェクトを通知するスクリプト エンジンで使用されるメソッドを提供します。 このインターフェイスは、プロファイラー オブジェクトによって実装されます。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)|プロファイラーのオブジェクト、スクリプト エンジンが DOM の関数呼び出しを実行することを通知します。|  
|[IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)|DOM の関数呼び出しを実行して、スクリプト エンジン オブジェクトが完了したら、プロファイラーに通知します。|  
  
## <a name="remarks"></a>Remarks  
 `IActiveScriptProfilerCallback2` Internet Explorer 9 と共にリリースされた最初のインターフェイス。  
  
 DOM への呼び出しではない関数呼び出しの通知がによって提供される、 [IActiveScriptProfilerCallback インターフェイス](../../winscript/reference/iactivescriptprofilercallback-interface.md)します。  
  
> [!NOTE]
>  プロファイリング、スクリプトが実行されているときに開始および停止する機能を追加するには、次のメソッドを呼び出します。 これらのメソッドを使用する場合、完全な呼び出し履歴を取得できます[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]開始またはプロファイリングを停止するときに実行します。  
> 
> - 呼び出す[IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md)をプロファイリングが開始したことをプロファイラーに通知します。  
>   -   呼び出す[IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md)をプロファイリングするをすぐに停止することをプロファイラーに通知します。  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト プロファイラーのインターフェイス](../../winscript/reference/active-script-profiler-interfaces.md)