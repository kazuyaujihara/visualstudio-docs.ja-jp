---
title: IActiveScriptProfilerControl インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 1448b394-9743-41b5-8eb9-5026a45773a4
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 86f4fb8dea97930f717800a14a27740b76eb6c2e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58160759"
---
# <a name="iactivescriptprofilercontrol-interface"></a>IActiveScriptProfilerControl インターフェイス
プロファイリングをサポートするスクリプト エンジンによって実装されます。 通常、実装するオブジェクト、`IActiveScriptProfilerControl`実装も、 [IActiveScript](../../winscript/reference/iactivescript.md)インターフェイス。 この場合を識別するハンドルを取得できます、`IActiveScriptProfilerControl`インターフェイスを呼び出すことによって、`IUnknown::QueryInterface`オブジェクトのメソッド。 インターフェイスは、停止とスクリプト エンジンのプロファイリングを開始するために必要なメソッドを提供します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptProfilerControl::StartProfiling](../../winscript/reference/iactivescriptprofilercontrol-startprofiling.md)|スクリプト エンジンのプロファイリングを開始します。|  
|[IActiveScriptProfilerControl::SetProfilerEventMask](../../winscript/reference/iactivescriptprofilercontrol-setprofilereventmask.md)|スクリプト エンジンで、profiler イベント マスクを設定します。|  
|[IActiveScriptProfilerControl::StopProfiling](../../winscript/reference/iactivescriptprofilercontrol-stopprofiling.md)|スクリプト エンジンのプロファイリングを停止します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト プロファイラーのインターフェイス](../../winscript/reference/active-script-profiler-interfaces.md)