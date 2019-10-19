---
title: T4 インクルード ディレクティブ
ms.date: 11/04/2016
ms.topic: reference
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 636260609aa535e3bc45efe0224a517fd782c040
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72606386"
---
# <a name="t4-include-directive"></a>T4 インクルード ディレクティブ

Visual Studio のテキストテンプレートでは、`<#@include#>` ディレクティブを使用して別のファイルのテキストを含めることができます。 `include` ディレクティブは、テキスト テンプレートに含まれる最初のクラス機能ブロック (`<#+ ... #>`) の前の任意の場所に配置できます。 インクルード ファイルに、`include` ディレクティブや他のディレクティブを含めることもできます。 これにより、テンプレート間でテンプレート コードや定型句を共有できるようになります。

## <a name="using-include-directives"></a>include ディレクティブの使用

```
<#@ include file="filePath" [once="true"] #>
```

- `filePath` には、絶対パスを指定することも、現在のテンプレート ファイルを基準とした相対パスを指定することもできます。

   また、特定の Visual Studio 拡張機能では、インクルードファイルを検索するための独自のディレクトリを指定できます。 たとえば、視覚化およびモデリング SDK (DSL ツール) がインストールされている場合、次のフォルダーがインクルードリストに追加されます: `Program Files\Microsoft Visual Studio 10.0\Common7\IDE\Extensions\Microsoft\DSL SDK\DSL Designer\11.0\TextTemplates`。

   追加されるこれらのインクルード フォルダーは、インクルード ファイルの拡張子によって異なります。 たとえば、DSL ツールのインクルード フォルダーは、インクルード ファイルの拡張子が `.tt` の場合にのみ追加されます。

- `filePath` には、"%" で区切られた環境変数を含めることもできます。 (例:

  ```
  <#@ include file="%HOMEPATH%\MyIncludeFile.t4" #>
  ```

- インクルード ファイルの名前に、拡張子 `".tt"` を使用する必要はありません。

   必要に応じて、インクルード ファイルには、`".t4"` など別の拡張子を使用できます。 これは、`.tt` ファイルをプロジェクトに追加すると、Visual Studio によってその**カスタムツール**プロパティが `TextTemplatingFileGenerator` に自動的に設定されるためです。 通常、インクルード ファイルを個別に変換することは望ましくありません。

   一方、ファイルの拡張子によって、インクルード ファイルの検索先となる追加フォルダーが決まる場合があることに注意してください。 これは、インクルード ファイルに他のファイルが含まれている場合に重要となります。

- インクルードされたコンテンツは、インクルード先のテキスト テンプレートに元から含まれていた場合とほとんど同じように処理されます。 ただし、`<#+...#>` ディレクティブの後に通常のテキスト ブロックと標準コントロール ブロックが続く場合でも、クラス機能ブロック (`include`) を含むファイルをインクルードすることができます。

- 複数のインクルードファイルから呼び出された場合でも、テンプレートが1回だけ含まれるようにするには、`once="true"` を使用します。

   この機能を使用すると、他のスニペットに既に含まれていることを気にせずに、再利用可能な T4 スニペットのライブラリを簡単に構築できます。  たとえば、テンプレートの処理とC#生成を処理する、非常に詳細なスニペットのライブラリがあるとします。  これらは、例外の生成など、タスク固有のいくつかのユーティリティによって使用されます。これは、それ以上のアプリケーション固有のテンプレートから使用できます。 依存関係グラフを描画すると、何回もインクルードされるスニペットがあることがわかります。 ただし、`once` パラメーターが指定されると、以降はインクルードが無効になります。

  **MyTextTemplate.tt:**

```
<#@ output extension=".txt" #>
Output message 1 (from top template).
<#@ include file="TextFile1.t4"#>
Output message 5 (from top template).
<#
   GenerateMessage(6); // defined in TextFile1.t4
   AnotherGenerateMessage(7); // defined in TextFile2.t4
#>
```

 **Textfile1.txt:**

```
   Output Message 2 (from included file).
<#@ include file="TextFile2.t4" #>
   Output Message 4 (from included file).
<#+ // Start of class feature control block.
void GenerateMessage(int n)
{
#>
   Output Message <#= n #> (from GenerateMessage method).
<#+
}
#>
```

 **Textfile2.txt:**

```
        Output Message 3 (from included file 2).
<#+ // Start of class feature control block.
void AnotherGenerateMessage(int n)
{
#>
       Output Message <#= n #> (from AnotherGenerateMessage method).
<#+
}
#>
```

 **生成されたファイル (MyTextTemplate .txt):**

```
Output message 1 (from top template).
   Output Message 2 (from included file).
        Output Message 3 (from included file 2).

   Output Message 4 (from included file).

Output message 5 (from top template).
   Output Message 6 (from GenerateMessage method).
       Output Message 7 (from AnotherGenerateMessage method).
```

## <a name="msbuild"></a>MSBuild および Visual Studio でのプロジェクトプロパティの使用
 Include ディレクティブでは $ (SolutionDir) などの Visual Studio マクロを使用できますが、MSBuild では動作しません。 ビルド コンピューターでテンプレートを変換する場合、代わりにプロジェクトのプロパティを使用する必要があります。

 .csproj ファイルまたは .vbproj ファイルを編集してプロジェクトのプロパティを定義します。 この例では、`myIncludeFolder` という名前のプロパティを定義します。

```xml
<!-- Define a project property, myIncludeFolder: -->
<PropertyGroup>
    <myIncludeFolder>$(MSBuildProjectDirectory)\..\libs</myIncludeFolder>
</PropertyGroup>

<!-- Tell the MSBuild T4 task to make the property available: -->
<ItemGroup>
    <T4ParameterValues Include="myIncludeFolder">
      <Value>$(myIncludeFolder)</Value>
    </T4ParameterValues>
  </ItemGroup>
```

 これで、Visual Studio および MSBuild の両方で正しく変換できるテキスト テンプレートでプロジェクトのプロパティを使用できます。

```
<#@ include file="$(myIncludeFolder)\defs.tt" #>
```
