---
title: TextTransform ユーティリティを使用したファイルの生成
ms.date: 07/26/2019
ms.topic: conceptual
helpviewer_keywords:
- text templates, TextTransform utility
- TextTransform.exe
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f1a12da7c7cae7e862d670b3f62fb801920f34e1
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72666727"
---
# <a name="generate-files-with-the-texttransform-utility"></a>TextTransform ユーティリティを使用してファイルを生成する

TextTransform は、テキストテンプレートを変換するために使用できるコマンドラインツールです。 TextTransform を呼び出す場合は、テキストテンプレートファイルの名前を引数として指定します。 TextTransform はテキスト変換エンジンを呼び出し、テキストテンプレートを処理します。 通常、TextTransform はスクリプトから呼び出されます。 ただし、通常は必要ありません。これは、Visual Studio またはビルド処理でテキスト変換を実行できるためです。

> [!NOTE]
> ビルド処理の一部としてテキスト変換を実行する場合は、MSBuild テキスト変換タスクの使用を検討してください。 詳細については、「[ビルドプロセスでのコード生成](../modeling/code-generation-in-a-build-process.md)」を参照してください。 Visual Studio がインストールされているコンピューターでは、テキストテンプレートを変換できるアプリケーションまたは Visual Studio 拡張機能を作成することもできます。 詳細については、「[カスタムホストを使用したテキストテンプレートの処理](../modeling/processing-text-templates-by-using-a-custom-host.md)」を参照してください。

TextTransform .exe は、次のディレクトリにあります。

::: moniker range=">=vs-2019"

**ファイル (x86) \Microsoft Visual Studio\2019\Professional\Common7\IDE**

Professional edition の場合は、または

**ファイル (x86) \Microsoft Visual Studio\2019\Enterprise\Common7\IDE**

Enterprise edition の場合。

::: moniker-end

::: moniker range="vs-2017"

**ファイル (x86) \Microsoft Visual Studio\2017\Professional\Common7\IDE**

Professional edition の場合は、または

**ファイル (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE**

Enterprise edition の場合。

以前のバージョンの Visual Studio では、ファイルは次の場所にあります。

**社内ファイル (x86) \ 一般的な方法 \ テンプレート \{version}**

ここで、{version} は、インストールされている以前のバージョンに依存します。

::: moniker-end

## <a name="syntax"></a>構文

```
TextTransform [<options>] <templateName>
```

### <a name="parameters"></a>パラメーター

|**引数**|**説明**|
|-|-|
|`templateName`|変換するテンプレートファイルの名前を指定します。|

|**オプション**|**説明**|
|-|-|
|**out** \<filename >|変換の出力の書き込み先のファイル。|
|**-r** \<assembly >|テキストテンプレートをコンパイルして実行するために使用されるアセンブリ。|
|**-u** \<namespace >|テンプレートをコンパイルするために使用される名前空間。|
|**-I** \<includedirectory >|指定したテキストテンプレートに含まれるテキストテンプレートを格納しているディレクトリ。|
|**-P** \<referencepath >|テキストテンプレート内で指定されたアセンブリを検索するディレクトリ。または、 **-r**オプションを使用する場合は。<br /><br /> たとえば、Visual Studio API に使用するアセンブリを含めるには、を使用します。<br /><br /> `-P "%VSSHELLFOLDER%\Common7\IDE\PublicAssemblies"`|
|**-dp** \<processorName >!\<className >!\<assemblyName&#124;コードベース >|テキストテンプレート内のカスタムディレクティブの処理に使用できるディレクティブプロセッサの名前、完全な型名、およびアセンブリ。|
|**-a** [processorname]![直接の Ename]\<parameterName >!\<parameterValue >|ディレクティブプロセッサのパラメーター値を指定します。 パラメーターの名前と値だけを指定した場合、パラメーターはすべてのディレクティブプロセッサで使用できるようになります。 ディレクティブプロセッサを指定する場合、パラメーターは、指定されたプロセッサでのみ使用できます。 ディレクティブ名を指定した場合、パラメーターは、指定されたディレクティブが処理されている場合にのみ使用できます。<br /><br /> ディレクティブプロセッサまたはテキストテンプレートからパラメーター値にアクセスするには、 [ITextTemplatingEngineHost](/previous-versions/visualstudio/visual-studio-2012/bb126369\(v\=vs.110\))を使用します。 テキストテンプレートで、テンプレートディレクティブに `hostspecific` を含め、`this.Host` でメッセージを呼び出します。 (例:<br /><br /> `<#@template language="c#" hostspecific="true"#> [<#= this.Host.ResolveParameterValue("", "", "parameterName") #>]`.<br /><br /> オプションのプロセッサ名とディレクティブ名を省略した場合でも、必ず '! ' マークを入力してください。 (例:<br /><br /> `-a !!param!value`|
|**-h**|ヘルプを提供します。|

## <a name="related-topics"></a>関連トピック

|タスク|トピック|
|-|-|
|Visual Studio ソリューションでファイルを生成します。|[T4 テキスト テンプレートを使用したデザイン時コード生成](../modeling/design-time-code-generation-by-using-t4-text-templates.md)|
|独自のデータ ソースを変換するためのディレクティブ プロセッサを作成する。|[T4 テキスト変換のカスタマイズ](../modeling/customizing-t4-text-transformation.md)|
|独自のアプリケーションからテキストテンプレートを呼び出すことができるテキストテンプレートホストを作成します。|[カスタム ホストを使用したテキスト テンプレートの処理](../modeling/processing-text-templates-by-using-a-custom-host.md)|
