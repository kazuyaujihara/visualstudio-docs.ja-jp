---
title: 元に戻したり、レガシ API を使用して再実行の管理 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a8a93b4fd12cd9a0bd2e5a5f3c70486e370545a9
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747642"
---
# <a name="manage-undo-and-redo-by-using-the-legacy-api"></a>元に戻すを管理し、従来の API を使用して再実行
エディターでは、ユーザーがコードを変更するときに、最近の変更内容を反転できるように元に戻す操作をサポートする必要があります。 ほとんどのエディターでは実装[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]と .NET Framework は、統合開発環境 (IDE) によって自動的に提供元に戻す機能を持つことができます。

## <a name="in-this-section"></a>このセクションの内容
- [方法: 元に戻す管理を実装](../extensibility/how-to-implement-undo-management.md)エディターの 1 つまたは複数のビューを元に戻す機能を提供します。

- [方法: 元に戻すスタックをクリア](../extensibility/how-to-clear-the-undo-stack.md)を元に戻すスタックをクリアする方法について説明します。

- [方法: リンクされた undo 管理を使用して、](../extensibility/how-to-use-linked-undo-management.md)組み込みますが、エディターに元に戻す管理をリンクします。

## <a name="reference"></a>参照
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager> 複数のビューをサポートしているのため元に戻す管理を提供します。
