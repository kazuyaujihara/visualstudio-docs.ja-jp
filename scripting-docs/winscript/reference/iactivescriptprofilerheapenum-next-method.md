---
title: Iactivescriptprofilerheapenum::next メソッド |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0336286f-1dcd-4df9-adf5-76b59b4e74bb
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4bad607db168d5f3e3533087c94c6c0970f5eb24
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58157608"
---
# <a name="iactivescriptprofilerheapenumnext-method"></a>IActiveScriptProfilerHeapEnum::Next メソッド
ヒープのオブジェクトのセット内の次のオブジェクトまたはオブジェクトの取得、 [iactivescriptprofilercontrol 3::enumheap メソッド](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Next (    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] PROFILER_HEAP_OBJECT** heapObjects,     [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `celt`  
 返されるオブジェクトの数。  
  
 `heapObjects`  
 [out]次[PROFILER_HEAP_OBJECT 構造体](../../winscript/reference/profiler-heap-object-structure.md)構造体。  
  
 `pceltFetched`  
 [out]返される、オブジェクトの数  
  
## <a name="return-value"></a>戻り値  
 HRESULT。