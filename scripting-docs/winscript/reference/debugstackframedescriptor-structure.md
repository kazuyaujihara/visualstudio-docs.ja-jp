---
title: DebugStackFrameDescriptor 構造体 |Microsoft Docs
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
ms.openlocfilehash: fddae48178ec6c56ce647f5c4f3a1bff3d81a980
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955195"
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
 スタック フレーム オブジェクト。  
  
 `dwMin`  
 このスタック フレームに関連付けられている物理アドレスの範囲のマシンに依存する表現。  
  
 `dwLim`  
 このスタック フレームに関連付けられている物理アドレスの上限までのマシンに依存する表現。  
  
 `fFinal`  
 フレームが処理されていることを示すフラグ。  
  
 `punkFinal`  
 このパラメーターがない場合`NULL`、マージ、現在の列挙子を停止して、新しいスレッドを開始する必要があります。 オブジェクトでは、新しい列挙を開始する方法を示します。  
  
## <a name="remarks"></a>Remarks  
 プロセス デバッグ マネージャーでは、この構造体を使用して複数のスクリプト エンジンからのスタック フレームを並べ替えます。 慣例により、ダウン スタックが増加します。 その結果、スタックが成長アーキテクチャでは、アドレスは、ある必要があります組を補完します。  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト デバッガーの定数、列挙型、および構造体](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)