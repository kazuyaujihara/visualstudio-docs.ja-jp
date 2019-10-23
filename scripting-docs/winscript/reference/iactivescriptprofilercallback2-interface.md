---
title: IActiveScriptProfilerCallback2 Interface |Microsoft Docs
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
ms.openlocfilehash: 25f9616497192659df67feedfe16bd9ea0c5e3b1
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577301"
---
# <a name="iactivescriptprofilercallback2-interface"></a>IActiveScriptProfilerCallback2 インターフェイス
ドキュメントオブジェクトモデル (DOM) イベントが発生したときにプロファイラーオブジェクトに通知するために、スクリプトエンジンによって使用されるメソッドを提供します。 このインターフェイスは、profiler オブジェクトによって実装されます。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)|スクリプトエンジンが DOM 関数呼び出しを実行しようとしていることをプロファイラーオブジェクトに通知します。|  
|[IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)|スクリプトエンジンが DOM 関数呼び出しの実行を終了したことをプロファイラーオブジェクトに通知します。|  
  
## <a name="remarks"></a>Remarks  
 @No__t_0 インターフェイスは、最初に Internet Explorer 9 と共にリリースされます。  
  
 DOM への呼び出しではない関数呼び出しの通知は、 [IActiveScriptProfilerCallback インターフェイス](../../winscript/reference/iactivescriptprofilercallback-interface.md)によって提供されます。  
  
> [!NOTE]
> スクリプトの実行時にプロファイリングを開始および停止する機能を追加するには、次のメソッドを呼び出します。 これらのメソッドを使用すると、プロファイリングの開始時または停止時に [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] が実行されている場合に、完全な呼び出し履歴を取得できます。  
> 
> - [IActiveScriptProfilerControl2:: CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md)を呼び出して、プロファイリングを開始したことをプロファイラーに通知します。  
>   - [IActiveScriptProfilerControl2::P repareprofilerstop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md)を呼び出して、プロファイリングをすぐに停止することをプロファイラーに通知します。  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト プロファイラーのインターフェイス](../../winscript/reference/active-script-profiler-interfaces.md)