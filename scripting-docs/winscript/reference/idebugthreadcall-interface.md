---
title: IDebugThreadCall インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugThreadCall interface
ms.assetid: 9a9a9892-f310-4ef3-8db2-4f868be52d7e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 89f0fba2f5210cdcf4bb8f17443f948cb9ba1f4e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63004861"
---
# <a name="idebugthreadcall-interface"></a>IDebugThreadCall インターフェイス
`IDebugThreadCall`インターフェイスは、通常のスレッド間の呼び出しを行うコンポーネントによって実装、`IDebugThread`プロセス デバッグ マネージャー (PDM) によって提供された実装をマーシャ リングします。  
  
 PDM 呼び出し、`IDebugThreadCall`インターフェイスで目的のスレッドと`IDebugThreadCall`インターフェイスが必要な実装への呼び出しをディスパッチします。 `IDebugThreadCall`インターフェイスが適切なページのトップへのパラメーターで渡されるパラメーター情報をキャストします。  
  
 `IDebugThreadCall`インターフェイスは、フリー スレッド オブジェクトです。  
  
## <a name="methods"></a>メソッド  
 継承されたメソッドだけでなく`IUnknown`、`IDebugThreadCall`インターフェイスは、次のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugThreadCall::ThreadCallHandler](../../winscript/reference/idebugthreadcall-threadcallhandler.md)|別のスレッドでコードを実行する呼び出しを処理します。|