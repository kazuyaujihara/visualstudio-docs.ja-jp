---
title: IActiveScript |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScript interface
ms.assetid: d8acee11-7f0d-4999-b97a-66774af16f71
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7a33db2bcbcb356a508fec2e6bc5449a899a1299
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577238"
---
# <a name="iactivescript"></a>IActiveScript
スクリプトエンジンを初期化するために必要なメソッドを提供します。 スクリプトエンジンは、`IActiveScript` インターフェイスを実装する必要があります。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScript::SetScriptSite](../../winscript/reference/iactivescript-setscriptsite.md)|ホストによって提供される[IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)サイトのスクリプトエンジンに通知します。|  
|[IActiveScript::GetScriptSite](../../winscript/reference/iactivescript-getscriptsite.md)|Windows スクリプトエンジンに関連付けられているサイトオブジェクトを取得します。|  
|[IActiveScript::SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md)|指定された状態にスクリプトエンジンを配置します。|  
|[IActiveScript::GetScriptState](../../winscript/reference/iactivescript-getscriptstate.md)|スクリプトエンジンの現在の状態を取得します。|  
|[IActiveScript::Close](../../winscript/reference/iactivescript-close.md)|スクリプトエンジンが現在読み込まれているスクリプトを破棄し、その状態を失わせ、他のオブジェクトに対するインターフェイスポインターを解放して、closed 状態にします。|  
|[IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md)|ルートレベルの項目の名前をスクリプトエンジンの名前空間に追加します。|  
|[IActiveScript::AddTypeLib](../../winscript/reference/iactivescript-addtypelib.md)|スクリプトの名前空間にタイプライブラリを追加します。|  
|[IActiveScript::GetScriptDispatch](../../winscript/reference/iactivescript-getscriptdispatch.md)|実行中のスクリプトの `IDispatch` インターフェイスを取得します。|  
|[IActiveScript::GetCurrentScriptThreadID](../../winscript/reference/iactivescript-getcurrentscriptthreadid.md)|現在実行中のスレッドのスクリプトエンジンで定義された識別子を取得します。|  
|[IActiveScript::GetScriptThreadID](../../winscript/reference/iactivescript-getscriptthreadid.md)|指定した Microsoft Win32 スレッドに関連付けられているスレッドのスクリプトエンジン定義の識別子を取得します。|  
|[IActiveScript::GetScriptThreadState](../../winscript/reference/iactivescript-getscriptthreadstate.md)|スクリプトスレッドの現在の状態を取得します。|  
|[IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)|実行中のスクリプトスレッドの実行を中断します。|  
|[IActiveScript::Clone](../../winscript/reference/iactivescript-clone.md)|現在のスクリプトエンジン (現在の実行状態を除く) を複製し、現在のスレッドにサイトを持たない読み込み済みのスクリプトエンジンを返します。|  
  
## <a name="see-also"></a>関連項目  
 [Windows スクリプト インターフェイスのリファレンス](../../winscript/reference/windows-script-interfaces-reference.md)