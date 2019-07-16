---
title: NotifyDebuggerOfWaitCompletion メソッド |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- NotifyDebuggerOfWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: 841c5908-4f3f-400b-a7b0-96a95f362817
caps.latest.revision: 6
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: bf0548e1e791c41d806ccc222176ee571b037389
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68153737"
---
# <a name="notifydebuggerofwaitcompletion-method"></a>NotifyDebuggerOfWaitCompletion メソッド
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

プレース ホルダー メソッドは、デバッガーがブレークポイント ターゲットとして使用します。 この方法には、インライン、または最適化されたできないする必要があります。  
  
 **名前空間:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **アセンブリ:** mscorlib (mscorlib.dll 内)  
  
## <a name="syntax"></a>構文  
  
```vb  
private void NotifyDebuggerOfWaitCompletion()  
```  
  
## <a name="remarks"></a>Remarks  
 タスクですべての結合操作は、デバッガー通知ビットが設定されている場合、このメソッドを呼び出す必要があります。  
  
## <a name="requirements"></a>必要条件  
  
## <a name="see-also"></a>関連項目  
 [Task クラス](../../extensibility/debugger/task-class-internal-members.md)
