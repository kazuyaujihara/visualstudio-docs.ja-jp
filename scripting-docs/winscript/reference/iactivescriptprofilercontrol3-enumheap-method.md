---
title: Iactivescriptprofilercontrol 3::enumheap メソッド |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 2799d06d-20dd-4c12-9646-554c0ea3606e
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6120b8fdd913b4acee2e3ee6774d770aa75b1f5a
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58147658"
---
# <a name="iactivescriptprofilercontrol3enumheap-method"></a>IActiveScriptProfilerControl3::EnumHeap メソッド
インターフェイスを返します ([IActiveScriptProfilerHeapEnum インターフェイス](../../winscript/reference/iactivescriptprofilerheapenum-interface.md))、関連付けられているスクリプト エンジンのコンテキストで GC ヒープ オブジェクトを反復処理に使用できます。  
  
 デバッグ モードまたはリリース モードでこのメソッドを呼び出すことができます。 このメソッドは、UI スレッドがアイドル状態のときに呼び出す必要があります。 以外のスクリプト エンジンに対して演算を実行していないメソッドが呼び出された後[iactivescriptprofilerheapenum::next メソッド](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)まで[iactivescriptprofilerheapenum::next メソッド](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)S_FALSE を返すまたは[IActiveScriptProfilerHeapEnum インターフェイス](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)インターフェイス ポインターを解放します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT EnumHeap([out] IActiveScriptProfilerHeapEnum** ppEnum);  
```  
  
#### <a name="parameters"></a>パラメーター  
 ppEnum  
 [out]返します、 [IActiveScriptProfilerHeapEnum インターフェイス](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)します。  
  
## <a name="return-value"></a>戻り値  
 HRESULT。