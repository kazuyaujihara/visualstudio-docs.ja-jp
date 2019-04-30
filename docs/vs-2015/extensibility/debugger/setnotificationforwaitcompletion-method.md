---
title: SetNotificationForWaitCompletion メソッド |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- SetNotificationForWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: da149c9a-20f4-4543-a29e-429c8c1d2e19
caps.latest.revision: 6
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 874e31c331f16e760e030f337dda715473b77af8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62423401"
---
# <a name="setnotificationforwaitcompletion-method"></a>SetNotificationForWaitCompletion メソッド
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

設定または TASK_STATE_WAIT_COMPLETION_NOTIFICATION 状態ビットをクリアします。  
  
 **名前空間:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **アセンブリ:** mscorlib (mscorlib.dll 内)  
  
## <a name="syntax"></a>構文  
  
```vb  
internal void SetNotificationForWaitCompletion(bool enabled)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `enabled`  
  
 `true` ビットを設定するには`false`未設定の状態ビット。  
  
## <a name="exceptions"></a>例外  
  
## <a name="remarks"></a>Remarks  
 デバッガーでは、非同期のメソッド本体の外部の手順を支援するには、このビットを設定します。 場合`enabled`は`true`、まだ完了されていないタスクにのみ、このメソッドを呼び出す必要があります。 場合`enabled`は`false`、完了したタスクでは、このメソッドを呼び出すことがあります。 いずれの場合、その必要がありますのみ使用 promise スタイルのタスクの。  
  
## <a name="requirements"></a>必要条件  
  
## <a name="see-also"></a>関連項目  
 [Task クラス](../../extensibility/debugger/task-class-internal-members.md)
