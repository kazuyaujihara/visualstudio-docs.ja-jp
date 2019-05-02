---
title: IProvideExpressionContexts インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IProvideExpressionContexts interface
ms.assetid: e4c70f2c-7d86-4fdc-a1cb-f5a0bb8ed037
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b6ec0d5e17b0d3527252352c2e789adfac4fa859
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63410061"
---
# <a name="iprovideexpressioncontexts-interface"></a>IProvideExpressionContexts インターフェイス
特定のコンポーネントによって認識されている式コンテキストを列挙する手段を提供します。 スクリプト エンジンは、通常、このインターフェイスを実装します。  
  
 プロセス デバッグ マネージャーでは、このインターフェイスを使用して、特定のスレッドに関連付けられているすべてのグローバル式のコンテキストを見つけます。  
  
> [!NOTE]
> このインターフェイスは、関心のあるスレッド内からを呼び出されます。 現在のスレッドを識別して適切な列挙子を返すために、実装者の責任です。  
  
## <a name="methods"></a>メソッド  
 継承されたメソッドだけでなく`IUnknown`、`IProvideExpressionContexts`インターフェイスは、次のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IProvideExpressionContexts::EnumExpressionContexts](../../winscript/reference/iprovideexpressioncontexts-enumexpressioncontexts.md)|このコンポーネントによって認識されている式コンテキストの列挙子を返します。|