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
ms.openlocfilehash: a987b4be3430f2ed8b0562f41b51a94797f96dc4
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58152185"
---
# <a name="iactivescriptparse"></a>IActiveScriptParse
Windows スクリプト エンジンをスクリプトに追加する未加工のテキスト コード スクリプトレットを許可またはにより、実行時に評価される式のテキストでは、実装されているか、`IActiveScriptParse`インターフェイス。 これにより、解釈されたスクリプト言語 VBScript などの独立したオーサリング環境がないために別のメカニズム (以外の`IPersist*`)、スクリプト エンジンにスクリプト コードを取得して、さまざまなオブジェクトにスクリプトの断片をアタッチするにはイベント。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptParse::InitNew](../../winscript/reference/iactivescriptparse-initnew.md)|スクリプト エンジンを初期化します。|  
|[IActiveScriptParse::AddScriptlet](../../winscript/reference/iactivescriptparse-addscriptlet.md)|コード スクリプトレットをスクリプトに追加します。|  
|[IActiveScriptParse::ParseScriptText](../../winscript/reference/iactivescriptparse-parsescripttext.md)|名前空間に宣言を追加して、適切なコードを評価する、指定したコード スクリプトレットを解析します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト インターフェイス](../../winscript/reference/active-script-interfaces.md)