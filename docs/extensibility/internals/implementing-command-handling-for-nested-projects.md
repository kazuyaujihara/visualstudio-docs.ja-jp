---
title: 入れ子になったプロジェクトのコマンド処理の実装 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- nested projects, implementing command handling
ms.assetid: 48a9d66e-d51c-4376-a95a-15796643a9f2
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 628fde153441104e4bb504253d96235270b4b8fb
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72727078"
---
# <a name="implementing-command-handling-for-nested-projects"></a>入れ子になったプロジェクト向けのコマンド処理の実装
IDE は、<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> および <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> インターフェイスを通じて渡されたコマンドを入れ子になったプロジェクトに渡すことができます。また、親プロジェクトはコマンドをフィルター処理またはオーバーライドできます。

> [!NOTE]
> 通常、親プロジェクトによって処理されるコマンドのみをフィルター処理できます。 IDE によって処理される**ビルド**や**配置**などのコマンドはフィルター処理できません。

 次の手順では、コマンド処理を実装するプロセスについて説明します。

## <a name="procedures"></a>手順

#### <a name="to-implement-command-handling"></a>コマンド処理を実装するには

1. 入れ子になったプロジェクトまたは入れ子になったプロジェクト内のノードをユーザーが選択すると、次のようになります。

   1. IDE は <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> メソッドを呼び出します。

      または

   2. ソリューションエクスプローラーのショートカットメニューコマンドなど、階層ウィンドウでコマンドが生成された場合、IDE はプロジェクトの親の <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> メソッドを呼び出します。

2. 親プロジェクトは、`pguidCmdGroup` や `prgCmds` などの `QueryStatus` に渡されるパラメーターを調べて、親プロジェクトがコマンドをフィルター処理する必要があるかどうかを判断できます。 フィルターコマンドに親プロジェクトが実装されている場合は、次のように設定する必要があります。

   ```
   prgCmds[0].cmdf = OLECMDF_SUPPORTED;
   // make sure it is disabled
   prgCmds[0].cmdf &= ~MSOCMDF_ENABLED;
   ```

    その後、親プロジェクトから `S_OK` が返されます。

    親プロジェクトがコマンドをフィルター処理しない場合は、`S_OK` を返すだけです。 この場合、IDE はコマンドを子プロジェクトに自動的にルーティングします。

    親プロジェクトは、子プロジェクトにコマンドをルーティングする必要がありません。 IDE がこのタスクを実行します。

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>
- [コマンド、メニュー、およびツール バー](../../extensibility/internals/commands-menus-and-toolbars.md)
- [入れ子になったプロジェクト](../../extensibility/internals/nesting-projects.md)