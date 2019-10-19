---
title: IActiveScriptProfilerControl Interface |Microsoft Docs
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
ms.openlocfilehash: ef127e3a4463d112b9ea424702fb2650c80cce7d
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571600"
---
# <a name="iactivescriptprofilercontrol-interface"></a>IActiveScriptProfilerControl インターフェイス
プロファイリングをサポートするスクリプトエンジンによって実装されます。 通常、`IActiveScriptProfilerControl` を実装するオブジェクトは、 [IActiveScript](../../winscript/reference/iactivescript.md)インターフェイスも実装します。 この場合は、オブジェクトの `IUnknown::QueryInterface` メソッドを呼び出すことによって、`IActiveScriptProfilerControl` インターフェイスへのハンドルを取得できます。 インターフェイスには、スクリプトエンジンでプロファイリングを停止および開始するために必要なメソッドが用意されています。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptProfilerControl::StartProfiling](../../winscript/reference/iactivescriptprofilercontrol-startprofiling.md)|スクリプトエンジンでのプロファイリングを開始します。|  
|[IActiveScriptProfilerControl::SetProfilerEventMask](../../winscript/reference/iactivescriptprofilercontrol-setprofilereventmask.md)|スクリプトエンジンでプロファイラーのイベントマスクを設定します。|  
|[IActiveScriptProfilerControl::StopProfiling](../../winscript/reference/iactivescriptprofilercontrol-stopprofiling.md)|スクリプトエンジンでのプロファイリングを停止します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト プロファイラーのインターフェイス](../../winscript/reference/active-script-profiler-interfaces.md)