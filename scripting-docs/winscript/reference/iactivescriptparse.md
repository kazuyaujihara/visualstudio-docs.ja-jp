---
title: IActiveScriptParse |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptParse interface
ms.assetid: 8c967d70-f582-4f64-9e79-49f40c4dcb7c
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 81f64352c15dce233058d49b70e35da7e2238688
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72561641"
---
# <a name="iactivescriptparse"></a>IActiveScriptParse
Windows スクリプトエンジンで、スクリプトに未加工のテキストコードのスクリプトを追加したり、実行時に式のテキストを評価したりできるようにするには、`IActiveScriptParse` インターフェイスを実装します。 VBScript など、独立した作成環境を持たない解釈されたスクリプト言語では、スクリプトコードをスクリプトエンジンに取り込み、さまざまなオブジェクトイベントにスクリプトフラグメントをアタッチするための代替メカニズム (`IPersist*` 以外) が用意されています.  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptParse::InitNew](../../winscript/reference/iactivescriptparse-initnew.md)|スクリプトエンジンを初期化します。|  
|[IActiveScriptParse::AddScriptlet](../../winscript/reference/iactivescriptparse-addscriptlet.md)|スクリプトにコードレットを追加します。|  
|[IActiveScriptParse::ParseScriptText](../../winscript/reference/iactivescriptparse-parsescripttext.md)|指定されたコードレットを解析し、名前空間に宣言を追加し、必要に応じてコードを評価します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト インターフェイス](../../winscript/reference/active-script-interfaces.md)