---
title: テキスト テンプレートを使用する方法 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: d1ac2509-0479-47eb-809c-1f171245d0b6
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9c31e1d17137fd0e801bb506c280a83285c311b4
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60093021"
---
# <a name="how-to--with-text-templates"></a>方法: テキスト テンプレートを使用する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

テキスト テンプレートで[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]の任意の種類のテキストを生成する便利な方法を提供します。 テキスト テンプレートを使用すると、アプリケーションの一部として実行時にテキストを生成したり、デザイン時にプロジェクト コードの一部を生成することができます。 このトピックでは、最も頻繁にまとめたものです"How do I..."よく寄せられる 質問します。  
  
 このトピックでは、ビュレットが付いている複数の回答は代替案です。  
  
 テキスト テンプレートの一般的な概要については、[コードの生成と T4 テキスト テンプレート](../modeling/code-generation-and-t4-text-templates.md)をお読みください。  
  
## <a name="how-to-"></a>操作方法。  
  
### <a name="generate-part-of-my-application-code"></a>アプリケーション コードの一部を生成  
 ファイルまたはデータベースにコンフィグレーションまたは*モデル*があります。 コードの 1 つ以上の部分が、そのモデルに依存しています。  
  
- テキスト テンプレートから、コード ファイルの一部を生成します。 詳細については、[T4 テキスト テンプレートを使用したデザイン時コード生成](../modeling/design-time-code-generation-by-using-t4-text-templates.md)と[テンプレートの作成を開始する最善の方法は何ですか?](#starting)を参照してください。  
  
### <a name="generate-files-at-run-time-passing-data-into-the-template"></a>テンプレートにデータを渡して、実行時にファイルを生成する  
 実行時に、アプリケーションは、標準のテキストとデータの組み合わせを含むレポートなどのテキスト ファイルを生成します。 何百もの `write` ステートメントを書くことを回避したいです。  
  
- ランタイム テキスト テンプレートをプロジェクトに追加します。 このテンプレートは、あなたのコードでインスタンス化しテキストを生成することができるクラスを作成します。 データは、コンストラクターのパラメーターから渡すことができます。 詳細については、次を参照してください。 [T4 テキスト テンプレートを使用した実行時テキスト生成](../modeling/run-time-text-generation-with-t4-text-templates.md)  
  
- 実行時にのみ使用可能なテンプレートを生成する場合は、標準のテキスト テンプレートを使用できます。 作成する場合、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]拡張機能で、テキスト テンプレート サービスを呼び出すことができます。 詳細については、次を参照してください。 [VS 拡張機能でテキスト変換を呼び出す](../modeling/invoking-text-transformation-in-a-vs-extension.md) 他のコンテキストで、テキスト テンプレート エンジンを使用することができます。 詳細については、「 <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName> 」を参照してください。  
  
     パラメーターをこれらのテンプレートに渡すには \<#@parameter#> ディレクティブを使用します。 詳細については、次を参照してください。 [T4 パラメーター ディレクティブ](../modeling/t4-parameter-directive.md)  
  
### <a name="read-another-project-file-from-a-template"></a>テンプレートから別のプロジェクト ファイルを読み取る  
 同じファイルの読み取りに[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]テンプレートとしてプロジェクト。  
  
- `hostSpecific="true"` ディレクティブに `<#@template#>` を挿入します。  
  
     コードで、ファイルの完全なパスを取得するために、`this.Host.ResolvePath(filename)` を使用します。  
  
### <a name="invoke-methods-from-a-template"></a>テンプレートからメソッドを呼び出す  
 標準[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] .NET Framework クラスなど、既に存在するメソッドの場合:  
  
- \<#@assembly ディレクティブを使用して、アセンブリをロードし、\<#@import#> を使用して名前空間のコンテキストを設定します。 詳細については、次を参照してください。 [T4 インポート ディレクティブ](../modeling/t4-import-directive.md)  
  
   頻繁に同じアセンブリのセットを使用し、ディレクティブをインポートする場合には、ディレクティブ プロセッサの作成を検討してください。 各テンプレートでは、アセンブリとモデル ファイルを読み込み、名前空間のコンテキストを設定できるディレクティブ プロセッサを呼び出すことができます。 詳細については、次を参照してください。[カスタム T4 テキスト テンプレート ディレクティブ プロセッサの作成](../modeling/creating-custom-t4-text-template-directive-processors.md)  
  
  自分で作成したメソッドの場合:  
  
- ランタイム テキスト テンプレートを作成する場合、ランタイム テキスト テンプレートと同じ名前を持つ部分クラス定義を記述します。 このクラスに、追加するメソッドを追加します。  
  
- メソッド、プロパティ、およびプライベートのクラス宣言ができるクラス機能コントロール ブロック `<#+ ... #>` を書きます。 そのテキスト テンプレートはコンパイル時に、クラスに変換されます。 標準コントロール ブロック `<#...#>` とテキストは、1 つのメソッドに変換され、クラス機能ブロックは別のメンバーとして挿入されます。 詳細については、次を参照してください。[テキスト テンプレートのコントロール ブロック](../modeling/text-template-control-blocks.md)  
  
   クラスの機能として定義されたメソッドは、埋め込みのテキスト ブロックとして含めることもできます。  
  
   別のファイルにクラスの機能を配置すること検討します。`<#@include#>` で1 つまたは複数のテンプレート ファイルにインクルードするこができます。  
  
- 別のアセンブリ (クラス ライブラリ) で、メソッドを記述し、テンプレートから呼び出します。 `<#@assembly#>` ディレクティブを使用してアセンブリを読み込み、`<#@import#>` を使用して名前空間のコンテキストを設定します。 注、それをデバッグするときに、アセンブリを再構築するためにする必要がありますを停止して再起動[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]します。 詳細については、次を参照してください。 [T4 テキスト テンプレート ディレクティブ](../modeling/t4-text-template-directives.md)  
  
### <a name="generate-many-files-from-one-model-schema"></a>1 つのモデル スキーマからの多数のファイル生成  
 同じXMLまたはデータベース スキーマを持つモデルからファイルをしばしば生成する場合:  
  
- ディレクティブ プロセッサを記述することを検討します。 これにより、アセンブリの複数のステートメントを置換して、単一のカスタム ディレクティブを持つ各テンプレート内でステートメントをインポートすることができます。 ディレクティブ プロセッサはモデル ファイルを読み込み、解析できます。 詳細については、次を参照してください。[カスタム T4 テキスト テンプレート ディレクティブ プロセッサの作成](../modeling/creating-custom-t4-text-template-directive-processors.md)  
  
### <a name="generate-files-from-a-complex-model"></a>複雑なモデルからファイルを生成する  
  
- ドメイン固有言語 (DSL) を表すモデルを作成することを検討してください。 これによって、モデル内の要素の名前を反映した型とプロパティを使用するため、テンプレートの記述が簡単になります。 ファイルを解析したり、XML ノードを巡回したりする必要はありません。 例えば:  
  
     `foreach (Book book in this.Library) { ... }`  
  
     詳細については、次を参照してください。[ドメイン固有言語の概要](../modeling/getting-started-with-domain-specific-languages.md)と[ドメイン固有言語からコードを生成する](../modeling/generating-code-from-a-domain-specific-language.md)  
  
- UML モデルからコードを生成することを検討してください。 コードは、UML を直接反映するためにはありません。 たとえば、UML モデル内の各クラスのクラスを生成する必要はありません。 代わりに、web サイトを表す UML クラス図を使用し、各 UML クラスから web ページを生成します。 お客様のニーズに最も近いダイアグラムの種類を選択します。 たとえば、任意の種類の作業の流れを表すアクティビティ図を選択します。 要素の種類ごとにアプリケーションに適した情報を追加するステレオタイプを定義できます。  
  
     UML モデルから生成する DSL の場合と同様に、独自のダイアグラムの種類を設計することがなくが、図表のフォームでは、モデルの編集を行ったりすることができます。  
  
     詳細については、次を参照してください。 [、アプリのモデルを作成](../modeling/create-models-for-your-app.md)と[UML モデルからファイルを生成](../modeling/generate-files-from-a-uml-model.md)します。  
  
### <a name="get-data-from-includevsprvsincludesvsprvs-mdmd"></a>データを取得します。 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]  
 提供されるサービスを使用する[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]、セットによって、`hostSpecific`属性と負荷、`EnvDTE`アセンブリ。 例えば:  
  
```csharp  
<#@ template hostspecific="true" language="C#" #>  
<#@ output extension=".txt" #>  
<#@ assembly name="EnvDTE" #>  
<#  
  IServiceProvider serviceProvider = (IServiceProvider)this.Host;  
  EnvDTE.DTE dte = (EnvDTE.DTE) serviceProvider.GetService(typeof(EnvDTE.DTE));  
#>  
  
Number of projects in this VS solution:  <#= dte.Solution.Projects.Count #>  
  
```  
  
### <a name="execute-text-templates-in-the-build-process"></a>ビルド プロセスでのテキスト テンプレートの実行  
  
- 詳細については、次を参照してください。[ビルド プロセスでのコード生成](../modeling/code-generation-in-a-build-process.md)   
  
## <a name="more-general-questions"></a>一般的な質問  
  
### <a name="starting"></a>テキスト テンプレートの作成を開始する最善の方法は何ですか?  
  
1. 生成されたファイルの具体的な例を記述します。  
  
2. `<#@template #>` ディレクティブを挿入することで、テキスト テンプレートに変えます。ディレクティブとコードは、入力ファイルまたはモデルを読み込むために必要です。  
  
3. 段階的に、ファイルの一部を式とコード ブロックに置き換えます。  
  
### <a name="what-is-a-model"></a>「モデル」とは何ですか?  
  
- テンプレートによって読み取られる入力です。 ファイルまたはデータベースが考えられます。 XML、Visio 図面、ドメイン固有言語 (DSL)、UML モデルのいずれか、またはプレーン テキストである可能性があります。 これは、いくつかのファイルにまたがることがあります。 通常は、複数のテンプレートが、1 つのモデルを読み取ります。  
  
     「モデル」という用語の意味は、プログラム コードやその他のファイルの生成というよりも、ビジネスの側面をより直接的に表現しています。 たとえば、生成されたソフトウェアが監督する通信ネットワークの計画を表しているかもしれません。  
  
### <a name="what-is-the-benefit-of-using-text-templates"></a>テキスト テンプレートを使用する利点は何ですか?  
 通常、1 つのモデルから複数のコードやその他のファイルを生成します。 モデルは、生成されるコードよりも直接的に要件を表しています。 実装の詳細を省略し、コードではなく、要件の観点から記述されます。 通常は – として、要件の変更とより簡単かつプログラム コードの別の部分よりも確実に、モデルを更新できます。  
  
 すなわち、コード生成は、アジャイル開発手法の観点から貴重なツールです。  
  
### <a name="what-best-practices-are-there-for-text-templates"></a>テキスト テンプレートには、どのような「ベスト プラクティス」がありますか?  
  
- 詳細については、次を参照してください。 [T4 テキスト テンプレートの記述に関するガイドライン](../modeling/guidelines-for-writing-t4-text-templates.md)します。  
  
### <a name="what-is-t4"></a>"T4"とは何ですか?  
  
- 別の名前、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]テキスト テンプレートの機能がここで説明します。 公開されていない以前のバージョンでは、「Text Template Transformation」の省略形でした。
