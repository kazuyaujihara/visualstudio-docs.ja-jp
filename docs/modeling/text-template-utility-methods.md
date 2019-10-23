---
title: テキスト テンプレートのユーティリティ メソッド
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- text templates, utility methods
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1e6426ea57fbdbec6ec47a4f6348463b88b250e0
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72606007"
---
# <a name="text-template-utility-methods"></a>テキスト テンプレートのユーティリティ メソッド

Visual Studio テキストテンプレートでコードを記述するときには、常に使用できるメソッドがいくつかあります。 これらのメソッドは <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation> で定義されています。

> [!TIP]
> また、ホスト環境によって提供される、通常の (前処理されていない) テキストテンプレートで、その他のメソッドやサービスを使用することもできます。 たとえば、ファイルパスを解決し、エラーをログに記録し、Visual Studio および読み込まれたパッケージによって提供されるサービスを取得することができます。 詳細については、「[テキストテンプレートから Visual Studio にアクセスする](/previous-versions/visualstudio/visual-studio-2010/gg604090\(v\=vs.100\))」を参照してください。

## <a name="write-methods"></a>メソッドの書き込み

式コードブロックを使用するのではなく、`Write()` および `WriteLine()` メソッドを使用して、標準コードブロック内にテキストを追加できます。 次の2つのコードブロックは機能的に同等です。

### <a name="code-block-with-an-expression-block"></a>式ブロックのあるコードブロック

```
<#
int i = 10;
while (i-- > 0)
    { #>
        <#= i #>
    <# }
#>
```

### <a name="code-block-using-writeline"></a>WriteLine () を使用したコードブロック

```
<#
    int i = 10;
    while (i-- > 0)
    {
        WriteLine((i.ToString()));
    }
#>
```

入れ子になった制御構造を持つ長いコードブロック内の式ブロックの代わりに、これらのユーティリティメソッドのいずれかを使用すると役に立つ場合があります。

@No__t_0 メソッドと `WriteLine()` メソッドには、2つのオーバーロードがあります。1つは、1つの文字列パラメーターを受け取り、もう1つは、複合書式指定文字列と、文字列に含めるオブジェクトの配列 (`Console.WriteLine()` メソッドなど) を受け取ります。 次の2つの `WriteLine()` の使用方法は機能的には同じです。

```
<#
    string msg = "Say: {0}, {1}, {2}";
    string s1 = "hello";
    string s2 = "goodbye";
    string s3 = "farewell";

    WriteLine(msg, s1, s2, s3);
    WriteLine("Say: hello, goodbye, farewell");
#>
```

## <a name="indentation-methods"></a>インデントメソッド

インデントメソッドを使用して、テキストテンプレートの出力を書式設定できます。 @No__t_0 クラスには、テキストテンプレートの現在のインデント、および追加されたインデントの一覧である `indentLengths` フィールドを示す `CurrentIndent` 文字列プロパティがあります。 @No__t_0 メソッドでインデントを追加し、`PopIndent()` メソッドでインデントを減算することができます。 すべてのインデントを解除する場合は、`ClearIndent()` メソッドを使用します。 次のコードブロックは、これらのメソッドの使用方法を示しています。

```
<#
    WriteLine(CurrentIndent + "Hello");
    PushIndent("    ");
    WriteLine(CurrentIndent + "Hello");
    PushIndent("    ");
    WriteLine(CurrentIndent + "Hello");
    ClearIndent();
    WriteLine(CurrentIndent + "Hello");
    PushIndent("    ");
    WriteLine(CurrentIndent + "Hello");
#>
```

このコードブロックでは、次の出力が生成されます。

```
Hello
        Hello
                Hello
Hello
        Hello
```

## <a name="error-and-warning-methods"></a>エラーと警告のメソッド

エラーと警告のユーティリティメソッドを使用して、Visual Studio エラー一覧にメッセージを追加できます。 たとえば、次のコードでは、エラー一覧にエラーメッセージを追加します。

```
<#
  try
  {
    string str = null;
    Write(str.Length.ToString());
  }
  catch (Exception e)
  {
    Error(e.Message);
  }
#>
```

## <a name="access-to-host-and-service-provider"></a>ホストおよびサービスプロバイダーへのアクセス

プロパティ `this.Host` を使用すると、テンプレートを実行しているホストによって公開されているプロパティにアクセスできます。 @No__t_0 を使用するには、`<@template#>` ディレクティブで `hostspecific` 属性を設定する必要があります。

`<#@template ... hostspecific="true" #>`

@No__t_0 の種類は、テンプレートが実行されているホストの種類によって異なります。 Visual Studio で実行されているテンプレートでは、`this.Host` を `IServiceProvider` にキャストして、IDE などのサービスにアクセスできます。 (例:

```
EnvDTE.DTE dte = (EnvDTE.DTE) ((IServiceProvider) this.Host)
                       .GetService(typeof(EnvDTE.DTE));
```

## <a name="using-a-different-set-of-utility-methods"></a>別のユーティリティメソッドのセットの使用

テキスト生成プロセスの一環として、テンプレートファイルはクラスに変換されます。このクラスは常に <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation> から継承さ `GeneratedTextTransformation`and 名前が付けられます。 代わりに別のメソッドのセットを使用する場合は、独自のクラスを記述し、テンプレートディレクティブで指定できます。 クラスは <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation> から継承する必要があります。

```
<#@ template inherits="MyUtilityClass" #>
```

@No__t_0 ディレクティブを使用して、コンパイル済みクラスが見つかるアセンブリを参照します。