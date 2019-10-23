---
title: ドメイン固有言語からのコードの生成 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: e3706cc9-2afd-456a-a879-68425a248ebc
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 32cafb9e68fc2535ed3b570022a59d284f4c4cae
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72666109"
---
# <a name="generating-code-from-a-domain-specific-language"></a>ドメイン固有言語からのコード生成
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Microsoft [!INCLUDE[dsl](../includes/dsl-md.md)] は、モデルで表されるデータからコード、ドキュメント、構成ファイル、およびその他の成果物を生成するための強力な方法を提供します。 @No__t_0 を使用すると、データを表すクラスのセットを作成できます。また、名前とプロパティにそのデータが反映されたクラスにテキストテンプレートを記述することもできます。

 たとえば、Fabrikam には、顧客名と電子メールアドレスの XML ファイルがあります。 開発者は、顧客がクラスであり、プロパティ名と電子メールを含むモデルを作成します。 データを処理するために複数のテキストテンプレートを記述します。このフラグメントを使用すると、すべての顧客のテーブルが HTML ページの一部として生成されます。

```
<table>
<# foreach (Customer c in ContactList) {  #>
  <tr><td> <#= c.FullName #> </td>
      <td> <#= c.EmailAddress #> </td> </tr>
<# } #>  </table>
```

 顧客データベースが処理されると、XML ファイルがモデルストアに読み込まれます。 @No__t_1 を使用して作成された*ディレクティブプロセッサ*を使用すると、テキストテンプレートのコードで Customer クラスを使用できるようになります。 多くのテキストテンプレートは、同じストアに対して実行できます。

 テキストテンプレートは、[!INCLUDE[dsl](../includes/dsl-md.md)] するために不可欠です。 これらは、ドメインモデルの要素のソースコードだけでなく、ツールを [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] と統合するために使用される VSPackage およびコントロールのソースコードを生成するために使用されます。

 ここでは、[!INCLUDE[dsl](../includes/dsl-md.md)] で使用されるテキストテンプレートを作成、変更、およびデバッグする方法のいくつかについて説明します。

## <a name="in-this-section"></a>このセクションの内容
 [テキスト テンプレートからモデルへのアクセス](../modeling/accessing-models-from-text-templates.md)

 テキストテンプレートでドメイン固有言語を参照する方法についての基本的な情報を提供します。

 [チュートリアル: モデルにアクセスするテキスト テンプレートのデバッグ](../modeling/walkthrough-debugging-a-text-template-that-accesses-a-model.md)

 ドメイン固有言語を参照するテキストテンプレートでトラブルシューティングとデバッグを行う方法について説明します。

 [チュートリアル: 生成済みディレクティブ プロセッサへのホストの接続](../modeling/walkthrough-connecting-a-host-to-a-generated-directive-processor.md)

 生成されたディレクティブプロセッサにカスタムホストを接続する方法について説明します。

 [DslTextTransform コマンド](../modeling/the-dsltexttransform-command.md)

 ドメイン固有言語を参照するテキストテンプレートのコマンドラインで TextTransform 実行可能ファイルを実行するコマンドファイルについて説明します。

## <a name="reference"></a>参照
 [T4 テキスト テンプレートの作成](../modeling/writing-a-t4-text-template.md)

 テキストテンプレートディレクティブとコントロールブロックの構文を提供します。

## <a name="related-sections"></a>関連項目
 [T4 テキスト テンプレートを使用したデザイン時コード生成](../modeling/design-time-code-generation-by-using-t4-text-templates.md)

 テキストテンプレート変換プロセスについて説明します。

 [ビルド処理でのコード生成](../modeling/code-generation-in-a-build-process.md)

 ビルドサーバーで DSL からファイルを生成する場合は、このトピックをお読みください。
