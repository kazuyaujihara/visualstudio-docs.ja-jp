---
title: GetTaskSchedulersForDebugger メソッド |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- GetTaskSchedulersForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 58aa236a-5ab8-4695-b303-89dffdbcd946
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 995bf40669a4480f6f1ddfe8071a7885a4659c9f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975585"
---
# <a name="gettaskschedulersfordebugger-method"></a>GetTaskSchedulersForDebugger メソッド
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

すべての配列を取得します<xref:System.Threading.Tasks.TaskScheduler>現在アクティブなオブジェクト。  
  
 **名前空間:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **アセンブリ:** mscorlib (mscorlib.dll 内)  
  
 .NET Framework からこの内部メンバーにアクセスできないため、次の構文には共通中間言語 (CIL) が提供されます。  
  
## <a name="syntax"></a>構文  
  
```  
.method assembly hidebysig static class System.Threading.Tasks.TaskScheduler[] GetTaskSchedulersForDebugger() cil managed  
```  
  
## <a name="return-value"></a>戻り値  
 すべての配列<xref:System.Threading.Tasks.TaskScheduler>これで現在アクティブなオブジェクト<xref:System.AppDomain>します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドはスレッド セーフでないしの他のインスタンスと同時に使用する必要があります<xref:System.Threading.Tasks.TaskScheduler>します。 デバッガーがその他のすべてのスレッドを中断された場合にのみ、デバッガーから呼び出すことはできます。  
  
## <a name="see-also"></a>関連項目  
 [TaskScheduler クラス](../../extensibility/debugger/taskscheduler-class-internal-members.md)
