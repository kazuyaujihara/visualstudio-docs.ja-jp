---
title: IActiveScriptErrorDebug インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptErrorDebug interface
ms.assetid: e5d50427-c033-4138-ac6e-3b2dfb3b750a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 936770859d3bdfe81c84245d32ae63346b142a01
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58153748"
---
# <a name="iactivescripterrordebug-interface"></a>IActiveScriptErrorDebug インターフェイス
コンパイル時エラーとランタイム例外のドキュメントのコンテキスト情報を提供します。 `IActiveScriptError::QueryInterface`メソッドのサポート、`IActiveScriptErrorDebug`インターフェイス。  
  
 継承されたメソッドだけでなく`IActiveScriptError`、`IActiveScriptErrorDebug`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptErrorDebug::GetDocumentContext](../../winscript/reference/iactivescripterrordebug-getdocumentcontext.md)|このエラーは、ドキュメントのコンテキストを提供します。|  
|[IActiveScriptErrorDebug::GetStackFrame](../../winscript/reference/iactivescripterrordebug-getstackframe.md)|ランタイム エラーを有効になっているスタック フレームを提供します。|