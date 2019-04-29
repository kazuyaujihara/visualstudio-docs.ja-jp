---
title: IActiveScriptProfilerControl5 インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 7fd0ce34-6ae3-428f-ba90-3e86a8a98ed0
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dacca8e8bf161b6f3a84dc216596673d5df8258c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992900"
---
# <a name="iactivescriptprofilercontrol5-interface"></a>IActiveScriptProfilerControl5 インターフェイス
スクリプト エンジンに関連付けられた GC ヒープ オブジェクトを列挙するメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```cpp
interface IActiveScriptProfilerControl5 : IActiveScriptProfilerControl4  
```  
  
## <a name="methods"></a>メソッド  
 [IActiveScriptProfilerControl5::EnumHeap2 メソッド](../../winscript/reference/iactivescriptprofilercontrol5-enumheap2-method.md)  
 インターフェイスを返します ([IActiveScriptProfilerHeapEnum インターフェイス](../../winscript/reference/iactivescriptprofilerheapenum-interface.md))、関連付けられているスクリプト エンジンのコンテキストで GC ヒープ オブジェクトを反復処理に使用できます。