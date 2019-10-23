---
title: T4 パラメーター ディレクティブ
ms.date: 11/04/2016
ms.topic: reference
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a4a9ea9d3c1f80c669ec52936969ae38342e6343
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72606180"
---
# <a name="t4-parameter-directive"></a>T4 パラメーター ディレクティブ

Visual Studio テキストテンプレートでは、`parameter` ディレクティブは、外部コンテキストから渡された値から初期化されるテンプレートコード内のプロパティを宣言します。 テキスト変換を呼び出すコードを記述する場合は、これらの値を設定できます。

## <a name="using-the-parameter-directive"></a>Parameter ディレクティブの使用

```
<#@ parameter type="Full.TypeName" name="ParameterName" #>
```

 @No__t_0 ディレクティブは、外部コンテキストから渡された値から初期化されるテンプレートコード内のプロパティを宣言します。 テキスト変換を呼び出すコードを記述する場合は、これらの値を設定できます。 値は、`Session` ディクショナリまたは <xref:System.Runtime.Remoting.Messaging.CallContext> で渡すことができます。

 リモート処理可能な型のパラメーターを宣言できます。 つまり、型は <xref:System.SerializableAttribute> で宣言するか、<xref:System.MarshalByRefObject> から派生する必要があります。 これにより、テンプレートが処理される AppDomain にパラメーター値を渡すことができます。

 たとえば、次の内容を含むテキストテンプレートを作成できます。

```
<#@ template language="C#" #>

<#@ parameter type="System.Int32" name="TimesToRepeat" #>

<# for (int i = 0; i < TimesToRepeat; i++) { #>
Line <#= i #>
<# } #>
```

## <a name="passing-parameter-values-to-a-template"></a>テンプレートにパラメーター値を渡す
 メニューコマンドやイベントハンドラーなどの Visual Studio 拡張機能を作成する場合は、テキストテンプレートサービスを使用してテンプレートを処理できます。

```csharp
// Get a service provider - how you do this depends on the context:
IServiceProvider serviceProvider = dte; // or dslDiagram.Store, for example
// Get the text template service:
ITextTemplating t4 = serviceProvider.GetService(typeof(STextTemplating)) as ITextTemplating;
ITextTemplatingSessionHost host = t4 as ITextTemplatingSessionHost;
// Create a Session in which to pass parameters:
host.Session = host.CreateSession();
// Add parameter values to the Session:
session["TimesToRepeat"] = 5;
// Process a text template:
string result = t4.ProcessTemplate("MyTemplateFile.t4",
  System.IO.File.ReadAllText("MyTemplateFile.t4"));
```

## <a name="passing-values-in-the-call-context"></a>呼び出しコンテキストで値を渡す
 または、<xref:System.Runtime.Remoting.Messaging.CallContext> で論理データとして値を渡すこともできます。

 次の例では、両方のメソッドを使用して値を渡します。

```csharp
ITextTemplating t4 = this.Store.GetService(typeof(STextTemplating)) as ITextTemplating;
ITextTemplatingSessionHost host = t4 as ITextTemplatingSessionHost;
host.Session = host.CreateSession();
// Pass a value in Session:
host.Session["p1"] = 32;
// Pass another value in CallContext:
System.Runtime.Remoting.Messaging.CallContext.LogicalSetData("p2", "test");

// Process a small template inline:
string result = t4.ProcessTemplate("",
   "<#@parameter type=\"System.Int32\" name=\"p1\"#>"
 + "<#@parameter type=\"System.String\" name=\"p2\"#>"
 + "Test <#=p1#> <#=p2#>");

// Result value is:
//     Test 32 test
```

## <a name="passing-values-to-a-run-time-preprocessed-text-template"></a>実行時 (前処理済み) テキストテンプレートに値を渡す
 通常、実行時 (前処理済み) テキストテンプレートでは、`<#@parameter#>` ディレクティブを使用する必要はありません。 代わりに、生成されたコードの追加のコンストラクターまたは設定可能なプロパティを定義して、パラメーター値を渡すことができます。 詳細については、「 [T4 テキストテンプレートを使用した実行時テキスト生成](../modeling/run-time-text-generation-with-t4-text-templates.md)」を参照してください。

 ただし、実行時テンプレートで `<#@parameter>` を使用する場合は、セッションディクショナリを使用して値を渡すことができます。 例として、`PreTextTemplate1` と呼ばれる前処理済みテンプレートとしてファイルを作成したとします。 次のコードを使用して、プログラムでテンプレートを呼び出すことができます。

```csharp
PreTextTemplate1 t = new PreTextTemplate1();
t.Session = new Microsoft.VisualStudio.TextTemplating.TextTemplatingSession();
t.Session["TimesToRepeat"] = 5;
// Add other parameter values to t.Session here.
t.Initialize(); // Must call this to transfer values.
string resultText = t.TransformText();
```

## <a name="obtaining-arguments-from-texttemplateexe"></a>TextTemplate .exe から引数を取得する

> [!IMPORTANT]
> @No__t_0 ディレクティブは `TextTransform.exe` ユーティリティの `-a` パラメーターで設定された値を取得しません。 これらの値を取得するには、`template` ディレクティブで `hostSpecific="true"` を設定し、`this.Host.ResolveParameterValue("","","argName")` を使用します。