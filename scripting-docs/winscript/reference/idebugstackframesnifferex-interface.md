---
title: IDebugStackFrameSnifferEx インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugStackFrameSnifferEx interface
ms.assetid: fd6cf744-dee7-45f2-9a90-355b90372923
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dccd9210908922951c20378868c33b3389cbed4f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432252"
---
# <a name="idebugstackframesnifferex-interface"></a>IDebugStackFrameSnifferEx インターフェイス
コンポーネントによって認識されている論理スタック フレームを列挙する手段を提供します。 スクリプト エンジンは、通常、このインターフェイスを実装します。 このインターフェイスのすべてのスタック フレームを検索するプロセス デバッグ マネージャーの使用は、特定のスレッドに関連付けられています。  
  
> [!NOTE]
> このインターフェイスは、関心のあるスレッド内からを呼び出されます。 インターフェイスの実装は、現在のスレッドを識別して、適切な列挙子を返す必要があります。  
  
 継承されたメソッドだけでなく`IDebugStackFrameSniffer`、`IDebugStackFrameSnifferEx`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugStackFrameSnifferEx::EnumStackFramesEx](../../winscript/reference/idebugstackframesnifferex-enumstackframesex.md)|現在のスレッドのスタック フレームの列挙子を返します。|