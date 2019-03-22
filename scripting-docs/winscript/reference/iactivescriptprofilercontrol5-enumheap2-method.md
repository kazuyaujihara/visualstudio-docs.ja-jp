---
title: Iactivescriptprofilercontrol 5::enumheap2 メソッド |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: a25859eb-ac28-4a97-bcb3-33788982a76b
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c90c536dee76d67fdb93dd205e8f6eedff6dcc7
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58150804"
---
# <a name="iactivescriptprofilercontrol5enumheap2-method"></a>IActiveScriptProfilerControl5::EnumHeap2 メソッド
インターフェイスを返します ([IActiveScriptProfilerHeapEnum インターフェイス](../../winscript/reference/iactivescriptprofilerheapenum-interface.md))、関連付けられているスクリプト エンジンのコンテキストで GC ヒープ オブジェクトを反復処理に使用できます。  
  
 デバッグ モードまたはリリース モードでこのメソッドを呼び出すことができます。 このメソッドは、UI スレッドがアイドル状態のときに呼び出す必要があります。 以外のスクリプト エンジンに対して演算を実行していないメソッドが呼び出された後[iactivescriptprofilerheapenum::next メソッド](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)まで[iactivescriptprofilerheapenum::next メソッド](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)S_FALSE を返すまたは[IActiveScriptProfilerHeapEnum インターフェイス](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)インターフェイス ポインターを解放します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT EnumHeap2(    [in] PROFILER_HEAP_ENUM_FLAGS enumFlags,    [out] IActiveScriptProfilerHeapEnum** ppEnum);  
```  
  
#### <a name="parameters"></a>パラメーター  
 enumFlags  
 オブジェクト リレーションシップ内でオブジェクトが指すものに関する補足情報を、公開するかどうかを指定する値です。 補足情報は、オブジェクトが Getter または Setter メソッドを指しているかを表す可能性があります。 詳細については、次を参照してください。 [PROFILER_HEAP_ENUM_FLAGS 列挙型](../../winscript/reference/profiler-heap-enum-flags-enumeration.md)します。  
  
 ppEnum  
 [out]返します、 [IActiveScriptProfilerHeapEnum インターフェイス](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)します。  
  
## <a name="return-value"></a>戻り値  
 HRESULT を返します。 次の値を指定できます。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|ヒープ列挙は正常に完了しました。|  
|`E_OUTOFMEMORY`|ヒープ列挙を実行するのに十分なメモリがありませんでした。|  
|`E_FAIL`|内部エラーが発生しました。|