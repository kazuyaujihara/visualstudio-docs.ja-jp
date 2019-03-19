---
title: IDebugExpressionContext インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpressionContext Interface
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpressionContext interface
ms.assetid: 52af82e8-0dec-49e2-a7f3-d00f66ca1401
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5920d644922b15f193ee396ea0c6bddb8a574698
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58156672"
---
# <a name="idebugexpressioncontext-interface"></a>IDebugExpressionContext インターフェイス
式を評価できるコンテキストを表します。 スタック フレーム オブジェクトは、このインターフェイスを実装します。  
  
 継承されたメソッドだけでなく`IUnknown`、`IDebugExpressionContext`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugExpressionContext::ParseLanguageText](../../winscript/reference/idebugexpressioncontext-parselanguagetext.md)|指定したテキストのデバッグの式を作成します。|  
|[IDebugExpressionContext::GetLanguageInfo](../../winscript/reference/idebugexpressioncontext-getlanguageinfo.md)|このコンテキストを所有している言語の名前と GUID を返します。|