---
title: 従来の言語サービスでのステートメント入力候補 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- statement completion
- language services, statement completion
ms.assetid: 617439dc-3f0e-4e5f-b346-3e4e7fcf3c1b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d4c813052892c21a6a3e04560452b503205df117
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72723222"
---
# <a name="statement-completion-in-a-legacy-language-service"></a>従来の言語サービスでのステートメント入力補完
ステートメント入力候補は、ユーザーがコアエディターで入力を開始した言語キーワードまたは要素をユーザーが終了するのを言語サービスが支援するプロセスです。 このトピックでは、ステートメントの入力候補の動作と、言語サービスでのその実装方法について説明します。

 従来の言語サービスは VSPackage の一部として実装されていますが、言語サービス機能を実装するための新しい方法として、MEF 拡張機能を使用することをお勧めします。 ステートメント入力候補を実装する新しい方法の詳細については、「[チュートリアル: ステートメント入力候補の表示](../../extensibility/walkthrough-displaying-statement-completion.md)」を参照してください。

> [!NOTE]
> できるだけ早く新しいエディター API の使用を開始することをお勧めします。 これにより、言語サービスのパフォーマンスが向上し、エディターの新機能を利用できるようになります。

## <a name="implementing-statement-completion"></a>ステートメント入力候補の実装
 コアエディターでは、ステートメント入力候補によって特殊な UI がアクティブ化され、コードを簡単に記述できるようになります。 ステートメント入力候補は、必要に応じて適切なオブジェクトまたはクラスを表示することによって役立ちます。これにより、特定の要素を記憶したり、ヘルプリファレンストピックで検索したりする必要がなくなります。

 ステートメント入力候補を実装するには、解析可能なステートメント完了トリガーを使用する必要があります。 たとえば、[!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] はドット (.) 演算子を使用し、[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] は矢印 (->) 演算子を使用します。 言語サービスでは、複数のトリガーを使用して、ステートメント入力候補を開始できます。 これらのトリガーは、コマンドフィルターでプログラミングされています。

## <a name="command-filters-and-triggers"></a>コマンドフィルターとトリガー
 コマンドフィルターは、トリガーまたはトリガーの発生をインターセプトします。 コマンドフィルターをビューに追加するには、<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> インターフェイスを実装し、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> メソッドを呼び出してビューにアタッチします。 ステートメント入力候補、エラーマーカー、メソッドヒントなど、言語サービスのすべての側面に対して同じコマンドフィルター (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>) を使用できます。 詳細については、「[従来の言語サービスコマンドのインターセプト](../../extensibility/internals/intercepting-legacy-language-service-commands.md)」を参照してください。

 エディター (具体的にはテキストバッファー) にトリガーを入力すると、言語サービスは <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> メソッドを呼び出します。 これにより、エディターによって UI が表示され、ユーザーはステートメント入力候補の候補から選択できるようになります。 このメソッドを使用するには、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> と <xref:Microsoft.VisualStudio.TextManager.Interop.UpdateCompletionFlags> フラグをパラメーターとして実装する必要があります。 完了項目の一覧がスクロールリストボックスに表示されます。 ユーザーが入力を続けると、リストボックス内の選択内容が更新され、最後に入力された文字に最も近い一致が反映されます。 コアエディターは、ステートメント入力候補用の UI を実装しますが、言語サービスでは、ステートメントの候補となる候補項目のセットを定義するために <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> インターフェイスを実装する必要があります。

## <a name="see-also"></a>関連項目
- [従来の言語サービスのコマンドの受信](../../extensibility/internals/intercepting-legacy-language-service-commands.md)