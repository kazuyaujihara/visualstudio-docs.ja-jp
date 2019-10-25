---
title: 単一ファイルジェネレーターの実装 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- custom tools, implementing
- projects [Visual Studio SDK], extensibility
- projects [Visual Studio SDK], managed custom tools
ms.assetid: fe9ef6b6-4690-4c2c-872c-301c980d17fe
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 69bde665e62d063b6bab8784634777eeea02e941
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72727176"
---
# <a name="implementing-single-file-generators"></a>単一ファイル ジェネレーターの実装
カスタムツール (単一ファイルジェネレーターと呼ばれることもあります) を使用して、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 内の [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] および [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] のプロジェクトシステムを拡張できます。 カスタムツールは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> インターフェイスを実装する COM コンポーネントです。 このインターフェイスを使用すると、カスタムツールによって1つの入力ファイルが1つの出力ファイルに変換されます。 変換の結果は、ソースコード、またはその他の有用な出力である可能性があります。 カスタムツールによって生成されるコードファイルの2つの例は、ビジュアルデザイナーの変更と、Web サービス記述言語 (WSDL) を使用して生成されたファイルに応答して生成されるコードです。

 カスタムツールが読み込まれたとき、または入力ファイルが保存されると、プロジェクトシステムは <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> メソッドを呼び出し、<xref:Microsoft.VisualStudio.Shell.Interop.IVsGeneratorProgress> コールバックインターフェイスへの参照を渡します。これにより、ツールが進行状況をユーザーに報告できるようになります。

 カスタムツールによって生成される出力ファイルは、入力ファイルに対する依存関係があるプロジェクトに追加されます。 カスタムツールの <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A> の実装によって返される文字列に基づいて、プロジェクトシステムによって出力ファイルの名前が自動的に決定されます。

 カスタムツールは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> インターフェイスを実装する必要があります。 必要に応じて、カスタムツールは、入力ファイル以外のソースから情報を取得するために <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite> インターフェイスをサポートします。 いずれの場合も、カスタムツールを使用する前に、システムまたは [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ローカルレジストリに登録する必要があります。 カスタムツールの登録の詳細については、「[単一ファイルジェネレーターの登録](../../extensibility/internals/registering-single-file-generators.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [ビジュアル デザイナーへのタイプの公開](../../extensibility/internals/exposing-types-to-visual-designers.md)