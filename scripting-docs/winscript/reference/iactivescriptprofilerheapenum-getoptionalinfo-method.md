---
title: Iactivescriptprofilerheapenum::getoptionalinfo メソッド |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 99ed9df5-71cf-4c25-b189-af9accc466ee
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab8096b79cfbb91e4b65256c84ab1ba01207d9ed
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992843"
---
# <a name="iactivescriptprofilerheapenumgetoptionalinfo-method"></a>IActiveScriptProfilerHeapEnum::GetOptionalInfo メソッド
指定したオブジェクトの省略可能な情報を取得します (から返されるヒープ オブジェクトのセットから、 [iactivescriptprofilercontrol 3::enumheap メソッド](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md))。  
  
 返されたオブジェクトに割り当てられている返されたメモリを解放する必要はありません。 代わりに、呼び出す必要がありますが、 [iactivescriptprofilerheapenum::freeobjectandoptionalinfo メソッド](../../winscript/reference/iactivescriptprofilerheapenum-freeobjectandoptionalinfo-method.md)します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetOptionalInfo (    [in] PROFILER_HEAP_OBJECT* heapObject,    [in] ULONG celt,    [out, size_is(celt)] PROFILER_HEAP_OBJECT_OPTIONAL_INFO* optionalInfo);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `heapObject`  
 [PROFILER_HEAP_OBJECT 構造体](../../winscript/reference/profiler-heap-object-structure.md)を情報を返します。  
  
 `celt`  
 数[PROFILER_HEAP_OBJECT_OPTIONAL_INFO 構造体](../../winscript/reference/profiler-heap-object-optional-info-structure.md)構造体を返します。  
  
 `optionalInfo`  
 [out]配列の[PROFILER_HEAP_OBJECT_OPTIONAL_INFO 構造体](../../winscript/reference/profiler-heap-object-optional-info-structure.md)指定したオブジェクトの構造体。  
  
## <a name="return-value"></a>戻り値  
 HRESULT。