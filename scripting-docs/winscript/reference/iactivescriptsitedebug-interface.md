---
title: IActiveScriptSiteDebug インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSiteDebug interface
ms.assetid: 2557ee09-688b-4c03-a821-180c24dfa0e6
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3cd8043648586ed3c614cbb137e51d992d7ae29b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992464"
---
# <a name="iactivescriptsitedebug-interface"></a>IActiveScriptSiteDebug インターフェイス
スマート ホストの実装、`IActiveScriptSiteDebug`ドキュメント管理を実行して、デバッグに参加するインターフェイス。 `IActiveScriptSite`オブジェクトは、通常の実装を提供します。、`IActiveScriptSiteDebug`インターフェイス。 この場合、呼び出し、`IActiveScriptSite::QueryInterface`メソッドを取得する、`IActiveScriptSiteDebug`インターフェイス。  
  
 継承されたメソッドだけでなく`IUnknown`、`IActiveScriptSiteDebug`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptSiteDebug::GetDocumentContextFromPosition](../../winscript/reference/iactivescriptsitedebug-getdocumentcontextfromposition.md)|委任に、言語エンジンによって使用される`IDebugCodeContext::GetSourceContext`します。|  
|[IActiveScriptSiteDebug::GetApplication](../../winscript/reference/iactivescriptsitedebug-getapplication.md)|このスクリプトのサイトに関連付けられたデバッグ アプリケーション オブジェクトを返します。|  
|[IActiveScriptSiteDebug::GetRootApplicationNode](../../winscript/reference/iactivescriptsitedebug-getrootapplicationnode.md)|スクリプト ドキュメントを追加する必要がありますアプリケーション ノードを取得します。|  
|[IActiveScriptSiteDebug::OnScriptErrorDebug](../../winscript/reference/iactivescriptsitedebug-onscripterrordebug.md)|により、スマート ホストは実行時エラーを処理する方法を決定します。|