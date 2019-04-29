---
title: レガシ言語サービスのコマンドをインターセプト |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands, intercepting language service
- language services, intercepting commands
ms.assetid: eea69f03-349c-44bb-bd4f-4925c0dc3e55
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eb53de9cf4d3056d9a07a915267391de27b753fb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62909615"
---
# <a name="intercepting-legacy-language-service-commands"></a>従来の言語サービスのコマンドの受信
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]、テキスト ビューの処理とそれ以外の場合、言語サービス インターセプト コマンドがあることができます。 これは、テキスト ビューが管理していない言語固有の動作に役立ちます。 テキスト ビューに、言語サービスから 1 つまたは複数のコマンドのフィルターを追加することで、これらのコマンドを傍受できます。

## <a name="getting-and-routing-the-command"></a>取得して、コマンドのルーティング
 コマンド フィルターは、<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>特定の文字のシーケンスまたはキーのコマンドを監視するオブジェクト。 コマンドの 1 つ以上のフィルターを 1 つのテキスト ビューと関連付けることができます。 各テキスト ビューでは、チェーンのコマンドのフィルターを保持します。 新しいコマンド フィルターを作成した後は、適切なテキスト ビューのチェーンに、フィルターを追加します。

 呼び出す、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A>メソッドを<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>チェーンに、コマンドのフィルターを追加します。 呼び出すと<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A>、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]コマンド フィルターが処理しないコマンドを渡せる別のコマンドのフィルターを返します。

 コマンド処理のため、次のオプションがあります。

- コマンドを処理し、チェーンの次のコマンドのフィルターにコマンドを渡します。

- コマンドを処理し、次のコマンドのフィルターにコマンドを渡さないでください。

- コマンドを処理しませんが、次のコマンドのフィルターにコマンドを渡します。

- コマンドを無視します。 現在のフィルター処理しないと、次のフィルターに渡されません。

  言語サービスを処理するコマンドの詳細については、次を参照してください。[言語サービス フィルターの重要なコマンド](../../extensibility/internals/important-commands-for-language-service-filters.md)します。