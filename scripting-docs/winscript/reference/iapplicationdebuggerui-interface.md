---
title: IApplicationDebuggerUI インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IApplicationDebuggerUI interface
ms.assetid: b8828817-ca24-4012-802c-7dcaeea65dc8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f138492e5b0a465bb0f101c15457ed1021ab3d5a
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58146178"
---
# <a name="iapplicationdebuggerui-interface"></a>IApplicationDebuggerUI インターフェイス
デバッガーの統合開発環境 (IDE) によって実装される (に加えて`IApplicationDebugger`)、外部コンポーネントに、デバッガーのユーザー インターフェイス (UI) より詳細に制御を提供します。  
  
 継承されたメソッドだけでなく`IUnknown`、`IApplicationDebuggerUI`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IApplicationDebuggerUI::BringDocumentToTop](../../winscript/reference/iapplicationdebuggerui-bringdocumenttotop.md)|デバッガーで最上位に指定されたデバッグ ドキュメントを含むウィンドウにユーザー インターフェイスを表示します。|  
|[IApplicationDebuggerUI::BringDocumentContextToTop](../../winscript/reference/iapplicationdebuggerui-bringdocumentcontexttotop.md)|デバッガーのユーザー インターフェイスの上部に特定のドキュメント コンテキストを含むウィンドウを表示し、コンテキストにウィンドウをスクロールします。|