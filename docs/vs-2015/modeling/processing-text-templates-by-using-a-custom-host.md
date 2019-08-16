---
title: カスタムホストを使用したテキストテンプレートの処理 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, in application or VS extension
- text templates, custom directive hosts
ms.assetid: affa3296-854d-47d6-9685-285f6d9ba5dc
caps.latest.revision: 35
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1c8f306315ad236843b6fcd5551d9aed13c26a92
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68871790"
---
# <a name="processing-text-templates-by-using-a-custom-host"></a>カスタム ホストを使用したテキスト テンプレートの処理
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

*テキスト テンプレート変換*処理は、*テキスト テンプレート*ファイルを入力とし、テキスト ファイルを出力として生成します。 テキスト変換エンジンは、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 拡張機能か、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] がインストールされているコンピューターで実行中のスタンドアロン アプリケーションから呼び出すことができます。 ただし、*テキスト テンプレート ホスト*を提供する必要があります。 このクラスは、テンプレートを環境に接続し、アセンブリやインクルード ファイルなどのリソースの検索と、出力およびエラー メッセージの処理を行います。

> [!TIP]
> [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 内で実行されるパッケージまたは拡張機能を作成する場合は、独自のホストを作成するのではなく、テキスト テンプレート サービスを使用することを検討します。 詳細については、次を参照してください。 [VS 拡張機能でテキスト変換を呼び出す](../modeling/invoking-text-transformation-in-a-vs-extension.md)

> [!NOTE]
> サーバー アプリケーションでテキスト テンプレート変換を使用することはお勧めしません。 また、シングル スレッド以外でテキスト テンプレート変換を使用することはお勧めしません。 テキスト テンプレート エンジンでは、単一の AppDomain を再利用して、テンプレートを変換、コンパイル、および実行するためです。 変換されたコードは、スレッド セーフになるように設計されているわけではありません。 デザイン時にはファイルは [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] プロジェクトに含まれているので、このエンジンはファイルを連続的に処理するように設計されています。
>
> ランタイム アプリケーションでは、前処理されたテキスト テンプレートの使用を検討してください。 次を参照してください。[T4 テキスト テンプレートを使用した実行時テキスト生成](../modeling/run-time-text-generation-with-t4-text-templates.md)

 コンパイル時に決定されるテンプレートのセットをアプリケーションで使用する場合は、前処理されたテキスト テンプレートを使用する方が簡単です。 この方法は、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] がインストールされていないコンピューターでアプリケーションを実行する場合にも使用できます。 詳細については、次を参照してください。 [T4 テキスト テンプレートを使用した実行時テキスト生成](../modeling/run-time-text-generation-with-t4-text-templates.md)

## <a name="executing-a-text-template-in-your-application"></a>アプリケーションでのテキスト テンプレートの実行
 テキスト テンプレートを実行するには、<xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName> の ProcessTemplate メソッドを呼び出します。

```
using Microsoft.VisualStudio.TextTemplating;
...
Engine engine = new Engine();
string output = engine.ProcessTemplate(templateString, host);
```

 アプリケーションでは、テンプレートを見つけて提供すると共に、出力を処理する必要があります。

 `host` パラメーターでは、[ITextTemplatingEngineHost](/previous-versions/visualstudio/visual-studio-2012/bb126505(v=vs.110)) を実装するクラスを指定する必要があります。 これはエンジンによってコールバックされます。

 ホストは、エラーのログ記録、アセンブリとインクルード ファイルへの参照の解決、テンプレートを実行できるアプリケーション ドメインの指定、各ディレクティブの適切なプロセッサの呼び出しを実行できる必要があります。

 <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName>は、 **VisualStudio\*で定義されています。0 .dll**と[ITextTemplatingEngineHost](/previous-versions/visualstudio/visual-studio-2012/bb126505(v=vs.110))は **\*VisualStudio で定義されています。0 .dll**。

## <a name="in-this-section"></a>このセクションの内容
 [チュートリアル: カスタムテキストテンプレートホスト](../modeling/walkthrough-creating-a-custom-text-template-host.md)の作成では、テキストテンプレート機能を外部[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]で使用できるようにするカスタムテキストテンプレートホストを作成する方法について説明します。

## <a name="reference"></a>参照
 [ITextTemplatingEngineHost](/previous-versions/visualstudio/visual-studio-2012/bb126505(v=vs.110))

## <a name="related-sections"></a>関連項目
 [テキストテンプレート変換プロセス](../modeling/the-text-template-transformation-process.md)テキスト変換のしくみと、カスタマイズできる部分について説明します。

 [カスタム T4 テキストテンプレートディレクティブプロセッサの作成](../modeling/creating-custom-t4-text-template-directive-processors.md)テキストテンプレートディレクティブプロセッサの概要について説明します。
