---
title: IActiveScriptProfilerCallback Interface |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 76f9164b-b086-4b29-ac79-76f9c76f1d11
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9ae520dcb36e00dfaba8702db6294a5a47484b0a
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571715"
---
# <a name="iactivescriptprofilercallback-interface"></a>IActiveScriptProfilerCallback インターフェイス
イベントの発生時にプロファイラーオブジェクトに通知するために、スクリプトエンジンによって使用されるメソッドを提供します。 このインターフェイスは、profiler オブジェクトによって実装されます。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptProfilerCallback::Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md)|プロファイリングをスクリプトエンジンで開始するときに、プロファイラーオブジェクトを初期化するために呼び出されます。|  
|[IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md)|スクリプトエンジンでプロファイリングが停止されたときに、プロファイラーオブジェクトを解放および解放するために呼び出されます。|  
|[IActiveScriptProfilerCallback::ScriptCompiled](../../winscript/reference/iactivescriptprofilercallback-scriptcompiled.md)|スクリプトエンジンによってスクリプトがコンパイルされたことをプロファイラーオブジェクトに通知します。|  
|[IActiveScriptProfilerCallback::FunctionCompiled](../../winscript/reference/iactivescriptprofilercallback-functioncompiled.md)|スクリプトをコンパイルするときに、スクリプトエンジンによって関数が検出されたことをプロファイラーオブジェクトに通知します。|  
|[IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md)|スクリプトエンジンがドキュメントオブジェクトモデル (DOM) への呼び出しではない関数呼び出しを実行しようとしていることをプロファイラーオブジェクトに通知します。|  
|[IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md)|スクリプトエンジンが DOM への呼び出しではない関数呼び出しの実行を完了したことをプロファイラーオブジェクトに通知します。|  
  
## <a name="remarks"></a>Remarks  
 ドキュメントオブジェクトモデル (DOM) への関数呼び出しの通知は、 [IActiveScriptProfilerCallback2 インターフェイス](../../winscript/reference/iactivescriptprofilercallback2-interface.md)によって提供されます。  
  
> [!NOTE]
> スクリプトの実行時にプロファイリングを開始および停止する機能を追加するには、次のメソッドを呼び出します。 これらのメソッドを使用すると、プロファイリングの開始時または停止時に [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] が実行されている場合に、完全な呼び出し履歴を取得できます。  
> 
> - [IActiveScriptProfilerControl2:: CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md)を呼び出して、プロファイリングを開始したことをプロファイラーに通知します。  
>   - [IActiveScriptProfilerControl2::P repareprofilerstop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md)を呼び出して、プロファイリングをすぐに停止することをプロファイラーに通知します。  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト プロファイラーのインターフェイス](../../winscript/reference/active-script-profiler-interfaces.md)