---
title: IDebugCodeContext インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugCodeContext interface
ms.assetid: ae1264d5-1ac2-4b04-9fa5-958212543975
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f3d3d1834d176a323778ae9b7d215951d1a26bb4
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58152578"
---
# <a name="idebugcodecontext-interface"></a>IDebugCodeContext インターフェイス
実行可能コード内の位置を表す抽象化です。  
  
 継承されたメソッドだけでなく`IUnknown`、`IDebugCodeContext`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugCodeContext::GetDocumentContext](../../winscript/reference/idebugcodecontext-getdocumentcontext.md)|このコードのコンテキストに関連付けられているドキュメント コンテキストを返します。|  
|[IDebugCodeContext::SetBreakPoint](../../winscript/reference/idebugcodecontext-setbreakpoint.md)|設定またはこのコードのコンテキストにブレークポイントをクリアします。|