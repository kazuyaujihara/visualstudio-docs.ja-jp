---
title: テキスト テンプレートのユーティリティ メソッド |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, utility methods
ms.assetid: 8c11f9f7-678b-4f0c-b634-dc78fda699d1
caps.latest.revision: 52
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 84f5b5de8b28062023d851e38e26930718d599e7
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58976571"
---
# <a name="text-template-utility-methods"></a>テキスト テンプレートのユーティリティ メソッド
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

コードを記述するときに使用可能な常にいくつかのメソッドがある、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]テキスト テンプレート。 これらのメソッドは、 <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation> で定義されています。  
  
> [!TIP]
>  通常の (前処理されていない) テキスト テンプレートにおいて、ホスト環境によって提供される他のメソッドとサービスを使用することもできます。 たとえば、ファイル パスを解決、エラーをログに記録してによって提供されるサービスを取得[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]といずれかのパッケージが読み込まれます。  詳細については、次を参照してください。[テキスト テンプレートから Visual Studio のへのアクセス](http://msdn.microsoft.com/0556f20c-fef4-41a9-9597-53afab4ab9e4)  
  
## <a name="write-methods"></a>メソッドを記述します。  
 式 コード ブロックを使用する代わりに、標準のコード ブロック内でテキストを追加する、`Write()`および`WriteLine()`メソッドを使うことができます。 次の 2 つのコード ブロックは、機能的に同等です。  
  
##### <a name="code-block-with-an-expression-block"></a>式ブロックを持つコード ブロック  
  
```  
<#  
int i = 10;  
while (i-- > 0)  
    { #>  
        <#= i #>  
    <# }  
#>  
```  
  
##### <a name="code-block-using-writeline"></a>WriteLine() を使用したコード ブロック  
  
```  
<#   
    int i = 10;  
    while (i-- > 0)  
    {   
        WriteLine((i.ToString()));  
    }  
#>  
```  
  
 入れ子になった制御構造を持つ長いコード ブロック内では、式ブロックの代わりにこれらのユーティリティ メソッドのいずれかを使用すると便利です。  
  
 `Write()`と`WriteLine()`メソッドは、(`Console.WriteLine()`メソッドと同じように) ひとつの文字列パラメーターをとるものと、複合書式指定文字列および文字列に含めるためのオブジェクトの配列をとるものの、2 つのオーバー ロードがあります。 次の 2 つの `WriteLine()` の使い方は機能的に同等です。  
  
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
  
## <a name="indentation-methods"></a>インデント メソッド  
 テキスト テンプレートの出力を整えるために、インデント メソッドを使用できます。 <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>クラスは、テキスト テンプレートでの現在のインデントの位置を示す `CurrentIndent` 文字列プロパティと、追加されたインデントのリストである `indentLengths` フィールドを持っています。 `PushIndent()`メソッドでインデントを追加し、`PopIndent()`メソッドでインデントを減らすことができます。 すべてのインデントを削除する場合は、`ClearIndent()`メソッドを使用します。 次のコード ブロックは、これらのメソッドの使用を示しています。  
  
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
  
 このコード ブロックは、次の出力を生成します。  
  
```  
Hello  
        Hello  
                Hello  
Hello  
        Hello  
```  
  
## <a name="error-and-warning-methods"></a>エラーと警告メソッド  
 エラーおよび警告のユーティリティ メソッドを使用してへのメッセージを追加することができます、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]エラー一覧。 たとえば、次のコードはエラー一覧に、エラー メッセージを追加します。  
  
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
  
## <a name="access-to-host-and-service-provider"></a>ホストとサービス プロバイダーへのアクセス  
 `this.Host` プロパティは、テンプレートを実行しているホストによって公開されるプロパティへのアクセスを提供します。 `this.Host`を使用するには、`<@template#>` ディレクティブの `hostspecific` 属性を設定する必要があります。  
  
 `<#@template ... hostspecific="true" #>`  
  
 `this.Host`の型は、テンプレートを実行しているホストの種類によって異なります。 実行されているテンプレートで[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]、キャストできます`this.Host`に`IServiceProvider`IDE などのサービスにアクセスします。 例えば:  
  
```  
EnvDTE.DTE dte = (EnvDTE.DTE) ((IServiceProvider) this.Host)  
                       .GetService(typeof(EnvDTE.DTE));  
```  
  
## <a name="using-a-different-set-of-utility-methods"></a>さまざまなユーティリティ メソッドの使用  
 テキスト生成処理の一環として、テンプレート ファイルはクラス（名前は常に `GeneratedTextTransformation` で、<xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>から継承しています）に変換されます。 代わりの別のメソッド セットを使用したい場合は、独自のクラスを記述し template ディレクティブで指定することができます。 クラスは、<xref:Microsoft.VisualStudio.TextTemplating.TextTransformation> を継承する必要があります。  
  
```  
<#@ template inherits="MyUtilityClass" #>  
```  
  
 コンパイル済みのクラスがあるアセンブリを参照するために、`assembly` ディレクティブを使用してください。
