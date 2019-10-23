---
title: Debugstackフレーム記述子の構造体 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DebugStackFrameDescriptor
apilocation:
- scrobj.dll
helpviewer_keywords:
- DebugStackFrameDescriptor structure
ms.assetid: a86bcb99-41e4-4a26-a1dd-e1458fb73139
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 910e08ec6d9982354eb71b50d5e916917808f140
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576553"
---
# <a name="debugstackframedescriptor-structure"></a>DebugStackFrameDescriptor 構造体
スタック フレームを列挙し、同じスレッドの複数の列挙型からの出力をマージします。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef struct tagDebugStackFrameDescriptor {  
   IDebugStackFrame *pdsf;  
   DWORD_PTR        dwMin;  
   DWORD_PTR        dwLim;  
   BOOL             fFinal;  
   IUnknown         *punkFinal;  
} DebugStackFrameDescriptor;  
```  
  
## <a name="members"></a>メンバー  
 `pdsf`  
 スタックフレームオブジェクト。  
  
 `dwMin`  
 このスタックフレームに関連付けられている物理アドレスの範囲の下限を示す、コンピューターに依存する表現。  
  
 `dwLim`  
 このスタックフレームに関連付けられている物理アドレスの範囲の上限を示す、コンピューターに依存する表現。  
  
 `fFinal`  
 フレームが処理されていることを示すフラグ。  
  
 `punkFinal`  
 このパラメーターが `NULL` されていない場合は、現在の列挙子のマージを停止し、新しい列挙子を開始する必要があります。 オブジェクトは、新しい列挙を開始する方法を示します。  
  
## <a name="remarks"></a>Remarks  
 プロセスデバッグマネージャーは、この構造体を使用して、複数のスクリプトエンジンからスタックフレームを並べ替えます。 慣例により、スタックはダウンします。 その結果、スタックが大きくなるアーキテクチャでは、アドレスを二重に補完する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト デバッガーの定数、列挙型、および構造体](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)