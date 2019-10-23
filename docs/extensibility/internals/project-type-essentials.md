---
title: プロジェクトの種類の要点 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project types [Visual Studio SDK]
ms.assetid: 09991589-2300-430e-b6a4-7f2b95fe676f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 435d3ca0e35911754cac1e37abb276939109a0b3
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72725401"
---
# <a name="project-type-essentials"></a>プロジェクト タイプの基本情報
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] には、[!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] や [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] などの言語用のプロジェクトの種類がいくつか含まれています。 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] では、独自のプロジェクトの種類を作成することもできます。

 カスタムコマンド、エディター、またはツールウィンドウを [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] に追加するだけの場合は、新しいプロジェクトの種類を作成しなくてもかまいません。 詳細については、以下のトピックを参照してください。

- [コマンド、メニュー、およびツール バー](../../extensibility/internals/commands-menus-and-toolbars.md)

- [エディターと言語サービスの拡張機能](../../extensibility/editor-and-language-service-extensions.md)

- [ツール ウィンドウの拡張とカスタマイズ](../../extensibility/extending-and-customizing-tool-windows.md)

  同様に、指定された [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] および [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] のプロジェクトの種類の動作をカスタマイズする場合は、プロジェクトのサブタイプを使用します。 詳細については、「[プロジェクトのサブタイプ](../../extensibility/internals/project-subtypes.md)」を参照してください。

  次の1つまたは複数をサポートする場合は、[!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 以外の言語に基づくプロジェクトの新しいプロジェクトの種類を作成する必要があります。

- Build

- 展開

- 複数の構成

- ソース管理

- デバッグ

- ソリューションエクスプローラー内のプロジェクト項目

- **[プロジェクトを開く]** または **[新しいプロジェクト]** ダイアログボックス

- プロジェクトの入れ子

- プロジェクトの種類の機能の詳細については、以下を参照してください。

- プロジェクトの種類は、VSPackage 内のオブジェクトであり、想定 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 一連のインターフェイスを実装します。 を使用してC#プロジェクトの種類を開発している場合、マネージパッケージフレームワークプロジェクトクラスは、必要なインターフェイスを実装し、その実装を継承できるようにします。 詳細については、「[マネージパッケージフレームワークを使用したプロジェクトのC#種類の実装」 ()](../../extensibility/internals/using-the-managed-package-framework-to-implement-a-project-type-csharp.md)を参照してください。

- 開発C++者にとって、HierUtil ライブラリのクラスは同様の方法で動作します。 詳細については、「[ビルド内にありません: HierUtil7 プロジェクトクラスを使用C++してプロジェクトの種類を実装する ()](https://msdn.microsoft.com/library/a5c16a09-94a2-46ef-87b5-35b815e2f346)」を参照してください。

- プロジェクトの種類では、.exe または .dll アセンブリに組み込まれている一般的なソースコードファイル以外のデータをサポートできます。 たとえば、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] データベースプロジェクトには、ディスクに格納されているスクリプトおよびクエリファイルへの参照が含まれており、データベースに対してスクリプトとクエリを実行するためのコマンドが**ソリューションエクスプローラー**に追加されますが、プロジェクトではビルド動作がサポートされていません。 詳細については、「[プロジェクト項目を開いて保存](../../extensibility/internals/opening-and-saving-project-items.md)する」を参照してください。

- プロジェクトの種類では、ファイルを使用する必要はありません。 たとえば、プロジェクトの種類では、すべてのデータをデータベースに格納できます。 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] を使用すると、プロジェクトおよびプロジェクト項目のデータを永続化する方法をプロジェクトの種類で完全に制御できます。 詳細については、「[プロジェクトの種類の設計](../../extensibility/internals/project-type-design-decisions.md)上の決定」を参照してください。

- プロジェクトの種類はプロジェクト*ファクトリ*を提供する必要があります。これは、そのプロジェクトの種類に基づいてプロジェクトを開くか作成するように [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] に指示されるたびに、プロジェクトの種類のインスタンスを作成するオブジェクトです。 詳細については、「[プロジェクトファクトリを使用したプロジェクトインスタンスの作成](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)」を参照してください。

- プロジェクトの種類では、プロジェクトおよびプロジェクト項目のテンプレートを指定する必要があります。 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] は、ユーザーが新しいプロジェクトを作成し、既存のプロジェクトに新しい項目を追加するときに、テンプレートを使用します。 詳細については、「[プロジェクトおよびプロジェクト項目テンプレートの追加](../../extensibility/internals/adding-project-and-project-item-templates.md)」を参照してください。

- プロジェクトの種類では、デバッグやリリースなどの複数の構成をサポートできます。 ユーザーは、指定したプロパティページを使用して、プロジェクトのさまざまな構成を変更できます。 詳細については、「[構成オプションの管理](../../extensibility/internals/managing-configuration-options.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [プロジェクト タイプの配置](../../extensibility/internals/deploying-project-types.md)