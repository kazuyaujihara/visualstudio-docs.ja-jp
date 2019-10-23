---
title: テンプレートポリシーと [プロパティ] ウィンドウ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Properties window, template policy
ms.assetid: 1d8019d3-5e57-47ba-b358-526b0796a63b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e7135a7c99f1566eaacb4079e9787cf2b5606682
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72722692"
---
# <a name="template-policy-and-the-properties-window"></a>テンプレート ポリシーとプロパティ ウィンドウ
エンタープライズテンプレートプロジェクト内にプロジェクトが含まれている場合、そのエンタープライズテンプレートプロジェクトでポリシーを適用できます。 テンプレートポリシーは、プロパティの既定値を設定したり、プロパティを非表示にしたり、プロパティを追加したりするために使用できる制約システムになります。

 テンプレートポリシーを使用して、 **[プロパティ]** ウィンドウでの情報の表示を制御することは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> の実装とは異なります。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> はコンポーネントレベルでオブジェクトのプロパティを処理しますが、テンプレートポリシーを使用して、ソリューションまたはプロジェクトレベルでオブジェクトのプロパティを制約できます。 要するにあの

- @No__t_0 にメソッドを実装して、特定のオブジェクトの **[プロパティ]** ウィンドウに表示される内容を決定します。

- ソリューションおよびプロジェクトレベルでテンプレートポリシーを使用して、以前に指定したオブジェクトの **[プロパティ]** ウィンドウに表示される内容を決定します。

  テンプレートポリシーを使用して、指定された種類のプロジェクト項目が**ソリューションエクスプローラー**で選択されている場合に、 **[プロパティ]** ウィンドウで特定のプロパティを選択的に制限することができます。これは、プロジェクトで作業している開発チームのすべてのメンバーに役立ちます。 たとえば、テンプレートポリシーを使用すると、開発者がデータベース内のすべての接続文字列情報を設定し、接続文字列を読み取り専用にすることができます。 このようにして、各開発者がデータアクセスに適切なパスを使用するようにするための簡単な方法を提供できます。

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>
- [プロパティの拡張](../../extensibility/internals/extending-properties.md)