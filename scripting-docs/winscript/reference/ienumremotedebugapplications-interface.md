---
title: IEnumRemoteDebugApplications インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IEnumRemoteDebugApplications interface
ms.assetid: ceb5fbe7-d131-4352-9dd1-af80acd3f3f7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 430551002bc7603d86f9c7fb624ec438734bd766
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963251"
---
# <a name="ienumremotedebugapplications-interface"></a>IEnumRemoteDebugApplications インターフェイス
アプリケーション オブジェクトを列挙します。 このインターフェイスは、"アプリケーションにアタッチ ダイアログ ボックスで、マシンで実行中のアプリケーションを列挙するために使用できます。  
  
 継承されたメソッドだけでなく`IUnknown`、`IEnumRemoteDebugApplications`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IEnumRemoteDebugApplications::Clone](../../winscript/reference/ienumremotedebugapplications-clone.md)|現在の列挙子と同じ状態を格納する列挙子を作成します。|  
|[IEnumRemoteDebugApplications::Next](../../winscript/reference/ienumremotedebugapplications-next.md)|指定された数の列挙体シーケンス内のセグメントを取得します。|  
|[IEnumRemoteDebugApplications::Reset](../../winscript/reference/ienumremotedebugapplications-reset.md)|先頭に、列挙体シーケンスをリセットします。|  
|[IEnumRemoteDebugApplications::Skip](../../winscript/reference/ienumremotedebugapplications-skip.md)|指定された数の列挙体シーケンス内のセグメントをスキップします。|