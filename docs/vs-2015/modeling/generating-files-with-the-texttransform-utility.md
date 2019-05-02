---
title: TextTransform ユーティリティを使用したファイルの生成 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, TextTransform utility
- TextTransform.exe
ms.assetid: 06a48235-fe02-403e-a1cf-2ae70b4db62f
caps.latest.revision: 43
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 607eda7550819e4150f026a0671ed744ba9c10a7
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63427043"
---
# <a name="generating-files-with-the-texttransform-utility"></a>TextTransform ユーティリティを使用したファイルの生成
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

TextTransform.exe は、テキスト テンプレートを変換するために使用できるコマンド ライン ツールです。 TextTransform.exe を呼び出すときに、引数として、テキスト テンプレート ファイルの名前を指定します。 TextTransform.exe では、テキスト変換エンジンを呼び出し、テキスト テンプレートを処理します。 TextTransform.exe は通常、スクリプトから呼び出されます。 ただし、Visual Studio あるいは、ビルド プロセスの中で、テキスト変換が実行されるため、通常、必須ではありません。  
  
> [!NOTE]
> ビルド プロセスの一部としてテキスト変換を実行する場合は、MSBuild のテキスト変換タスクの使用を検討してください。 詳細については、次を参照してください。[ビルド プロセスでのコード生成](../modeling/code-generation-in-a-build-process.md)  コンピューターでの[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]がインストールされているアプリケーションを記述することもできます。 または[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]テキスト テンプレートを変換できる拡張機能。 詳細については、[カスタム ホストを使用してテキスト テンプレートの処理](../modeling/processing-text-templates-by-using-a-custom-host.md)を参照してください。  
  
 TextTransform.exe は、次のディレクトリにあります。  
  
 **\Program Files\Common Files\Microsoft Shared\TextTemplating\11.0**  
  
## <a name="syntax"></a>構文  
  
```  
TextTransform [<options>] <templateName>  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|**引数**|**説明**|  
|------------------|---------------------|  
|`templateName`|変換するテンプレート ファイルの名前を示します。|  
  
|**オプション**|**説明**|  
|----------------|---------------------|  
|**-out** \<filename>|変換の出力を書き込むファイル。|  
|**-r** \<assembly>|テキスト テンプレートをコンパイルし実行するために使用するアセンブリ。|  
|**-u** \<namespace>|テンプレートのコンパイルに使用される名前空間。|  
|**-I** \<includedirectory>|テキスト テンプレートでインクルードすることが指定されたテキスト テンプレートが含まれるディレクトリ。|  
|**-P** \<referencepath>|テキスト テンプレート内、あるいは、 **-r** オプションで指定されたアセンブリを検索するディレクトリ。<br /><br /> たとえば、Visual Studio API を使用するアセンブリを含めるためには次のようにします。<br /><br /> `-P "%VSSHELLFOLDER%\Common7\IDE\PublicAssemblies"`|  
|**-dp** \<processorName>!\<className>!\<assemblyName&#124;codeBase>|テキスト テンプレートの中でカスタム ディレクティブの処理に使用できるディレクティブ プロセッサの名前、完全な型の名前、および、アセンブリ。|  
|**-** [processorName] [。directiveName]。\<parameterName >!\<parameterValue >|ディレクティブ プロセッサのパラメーター値を指定します。 パラメーター名と値のみを指定したパラメーターはすべてのディレクティブ プロセッサで利用できます。 ディレクティブ プロセッサを指定した場合、パラメーターが指定したプロセッサのみが使用できます。 ディレクティブの名前を指定する場合、パラメーターの値は、指定されたディレクティブが処理されている場合にのみ使用です。<br /><br />  テキスト テンプレート中に、`hostspecific` template ディレクティブを含め、`this.Host` 上のメッセージを呼び出します。 例えば:<br /><br /> `<#@template language="c#" hostspecific="true"#> [<#= this.Host.ResolveParameterValue("", "", "parameterName") #>]`。<br /><br /> 入力省略可能なプロセッサとディレクティブの名前を省略した場合でも、'!'マークは常にタイプします。  例えば:<br /><br /> `-a !!param!value`|  
|**-h**|ヘルプを提供します。|  
  
## <a name="related-topics"></a>関連トピック  
  
|タスク|トピック|  
|----------|-----------|  
|[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ソリューション内にファイルを生成する。|[T4 テキスト テンプレートを使用したデザイン時コード生成](../modeling/design-time-code-generation-by-using-t4-text-templates.md)|  
|独自のデータ ソースを変換するためのディレクティブ プロセッサを作成する。|[T4 テキスト変換のカスタマイズ](../modeling/customizing-t4-text-transformation.md)|  
|独自のアプリケーションからテキスト テンプレートを呼び出すことができるテキスト テンプレート ホストの作成。|[カスタム ホストを使用したテキスト テンプレートの処理](../modeling/processing-text-templates-by-using-a-custom-host.md)|
