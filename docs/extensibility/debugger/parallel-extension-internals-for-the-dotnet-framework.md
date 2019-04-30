---
title: .NET Framework の拡張機能の内部を並列 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, internals [.NET Framework]
ms.assetid: 93e07cfa-91fa-464c-b866-8bf5570411df
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0437363dd7d45b95a04a9e58edd45229f14b4c93
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925363"
---
# <a name="parallel-extension-internals-for-the-net-framework"></a>.NET Framework の並列拡張機能の内部
内部の型、メソッド、について説明し、できるようにするクラスのフィールドは、.NET Framework の parallel extensions のカスタムのデバッガーを実装します。

## <a name="in-this-section"></a>このセクションの内容
 [Task クラス](../../extensibility/debugger/task-class-internal-members.md)の内部データ メンバーについて説明します、<xref:System.Threading.Tasks.Task?displayProperty=fullName>クラス。

 [TaskScheduler クラス](../../extensibility/debugger/taskscheduler-class-internal-members.md)の内部データ メンバーについて説明します、<xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>クラス。

 [ContingentProperties クラス](../../extensibility/debugger/contingentproperties-class-internal-members.md)の内部データ メンバーについて説明します、`System.Threading.Tasks.ContingentProperties`クラス。

 [AsyncTaskMethodBuilder 構造](../../extensibility/debugger/asynctaskmethodbuilder-structure-internal-members.md)の内部メンバーについて説明します、<xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder>構造体。

 [AsyncTaskMethodBuilder\<TResult > 構造体](../../extensibility/debugger/asynctaskmethodbuilder-tresult-structure-internal-members.md)の内部メンバーについて説明します、<xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601>構造体。

 [AsyncVoidMethodBuilder 構造体](../../extensibility/debugger/asyncvoidmethodbuilder-structure-internal-members.md)の内部メンバーについて説明します、<xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder>構造体。

## <a name="see-also"></a>関連項目
- <xref:System.Threading.Tasks.Task?displayProperty=fullName>
- <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>
- [Visual Studio デバッガーの拡張性](../../extensibility/debugger/visual-studio-debugger-extensibility.md)
- [並列プログラミング](/dotnet/standard/parallel-programming/index)