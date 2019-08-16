---
title: カスタム ホストを使用したテキスト テンプレートの処理
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, in application or VS extension
- text templates, custom directive hosts
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f054bd91f16bb7621d4beebe7631a49cb406132e
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68870469"
---
# <a name="process-text-templates-by-using-a-custom-host"></a>カスタム ホストを使用したテキスト テンプレートの処理

*テキスト テンプレート変換*処理は、*テキスト テンプレート*ファイルを入力とし、テキスト ファイルを出力として生成します。 テキスト変換エンジンは、Visual Studio 拡張機能から、または Visual Studio がインストールされているコンピューターで実行されているスタンドアロンアプリケーションから呼び出すことができます。 ただし、*テキスト テンプレート ホスト*を提供する必要があります。 このクラスは、テンプレートを環境に接続し、アセンブリやインクルード ファイルなどのリソースの検索と、出力およびエラー メッセージの処理を行います。

> [!TIP]
> パッケージまたは Visual Studio 内で実行される拡張機能を記述する場合は、独自のホストを記述する代わりに、テキスト テンプレート サービスを使用することを検討します。 詳細については、次を参照してください。 [VS 拡張機能でテキスト変換を呼び出す](../modeling/invoking-text-transformation-in-a-vs-extension.md)

> [!NOTE]
> サーバー アプリケーションでテキスト テンプレート変換を使用することはお勧めしません。 また、シングル スレッド以外でテキスト テンプレート変換を使用することはお勧めしません。 テキスト テンプレート エンジンでは、単一の AppDomain を再利用して、テンプレートを変換、コンパイル、および実行するためです。 変換されたコードは、スレッド セーフになるように設計されているわけではありません。 エンジンは、Visual Studio プロジェクトのデザイン時のように、順番に処理するように設計されています。
>
> ランタイム アプリケーションでは、前処理されたテキスト テンプレートの使用を検討してください。 次を参照してください。[T4 テキスト テンプレートを使用した実行時テキスト生成](../modeling/run-time-text-generation-with-t4-text-templates.md)

コンパイル時に決定されるテンプレートのセットをアプリケーションで使用する場合は、前処理されたテキスト テンプレートを使用する方が簡単です。 Visual Studio がインストールされていないコンピューターで実行されるアプリケーションでも、このアプローチを使用することができます。 詳細については、次を参照してください。 [T4 テキスト テンプレートを使用した実行時テキスト生成](../modeling/run-time-text-generation-with-t4-text-templates.md)

## <a name="execute-a-text-template-in-your-application"></a>アプリケーションでテキストテンプレートを実行する

テキスト テンプレートを実行するには、<xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName> の ProcessTemplate メソッドを呼び出します。

```csharp
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
 [チュートリアル: カスタム テキスト テンプレート ホストの作成](../modeling/walkthrough-creating-a-custom-text-template-host.md)は、Visual Studio の外部テキスト テンプレートの機能を利用できるようにするカスタム テキスト テンプレート ホストを作成する方法を示します。

## <a name="reference"></a>参照
 [ITextTemplatingEngineHost](/previous-versions/visualstudio/visual-studio-2012/bb126505(v=vs.110))

## <a name="related-sections"></a>関連項目

- [テキスト テンプレート変換プロセス](../modeling/the-text-template-transformation-process.md)は、テキスト変換のしくみと、どの部分がカスタマイズ可能かを説明します。
- [カスタム T4 テキスト テンプレート ディレクティブ プロセッサの作成](../modeling/creating-custom-t4-text-template-directive-processors.md)は、テンプレート ディレクティブ プロセッサのテキストの概要を説明します。