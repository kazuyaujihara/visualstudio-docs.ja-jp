---
title: IDebugStackFrame インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugStackFrame interface
ms.assetid: e95c1b4f-17c1-490c-a56b-c25fa45d4822
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d8f645d6460ff15734348267b5138b1b6edea071
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63005879"
---
# <a name="idebugstackframe-interface"></a>IDebugStackFrame インターフェイス
スレッド スタック上の論理スタック フレームを表します。 呼び出す、`IDebugStackFrame::QueryInterface`メソッドを取得する、`IDebugExpressionContext`インターフェイスで、式の評価とウォッチ ウィンドウを使用します。  
  
 継承されたメソッドだけでなく`IUnknown`、`IDebugStackFrame`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugStackFrame::GetCodeContext](../../winscript/reference/idebugstackframe-getcodecontext.md)|スタック フレームに関連付けられている現在のコード コンテキストを返します。|  
|[IDebugStackFrame::GetDescriptionString](../../winscript/reference/idebugstackframe-getdescriptionstring.md)|スタック フレームの短い、または時間の長いテキストの説明を返します。|  
|[IDebugStackFrame::GetLanguageString](../../winscript/reference/idebugstackframe-getlanguagestring.md)|言語の短い、または時間の長いテキストの説明を返します。|  
|[IDebugStackFrame::GetThread](../../winscript/reference/idebugstackframe-getthread.md)|このスタック フレームに関連付けられているスレッドを返します。|  
|[IDebugStackFrame::GetDebugProperty](../../winscript/reference/idebugstackframe-getdebugproperty.md)|現在のフレームのプロパティ ブラウザーを返します。|