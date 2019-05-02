---
title: T4 テキスト テンプレートのディレクティブ
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, import directive
- text templates, include directive
- text templates, assembly directive
- text templates, output directive
- text templates, directives
- text templates, template directive
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e09f3a9dfcc6c26e9dd575f4a127884e28def1ef
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62856082"
---
# <a name="t4-text-template-directives"></a>T4 テキスト テンプレートのディレクティブ
ディレクティブは、テキスト テンプレート変換エンジンに対する命令です。

ディレクティブの構文は次のとおりです。

```
<#@ DirectiveName [AttributeName = "AttributeValue"] ... #>
```

属性値はすべて、二重引用符で囲む必要があります。 値そのものに引用符が含まれている場合は、\ 文字でエスケープする必要があります。

通常、ディレクティブはテンプレート ファイルまたはインクルード ファイル内の最初の要素となります。 コード ブロック (`<#...#>`) 内およびクラス機能ブロック (`<#+...#>`) の後に、ディレクティブを配置することはできません。

[T4 テンプレート ディレクティブ](../modeling/t4-template-directive.md)

```
<#@ template [language="VB"] [hostspecific="true|TrueFromBase"] [debug="true"] [inherits="templateBaseClass"] [culture="code"] [compilerOptions="options"] [visibility="internal"] [linePragmas="false"] #>
```

[T4 パラメーター ディレクティブ](../modeling/t4-parameter-directive.md)

```
<#@ parameter type="Full.TypeName" name="ParameterName" #>
```

[T4 出力ディレクティブ](../modeling/t4-output-directive.md)

```
<#@ output extension=".fileNameExtension" [encoding="encoding"] #>
```

[T4 アセンブリ ディレクティブ](../modeling/t4-assembly-directive.md)

```
<#@ assembly name="[assembly strong name|assembly file name]" #>
```

[T4 インポート ディレクティブ](../modeling/t4-import-directive.md)

```
<#@ import namespace="namespace" #>
```

[T4 インクルード ディレクティブ](../modeling/t4-include-directive.md)

```
<#@ include file="filePath" #>
```

[T4 CleanUpBehavior ディレクティブ](../modeling/t4-cleanupbehavior-directive.md)

```
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>
```

独自のディレクティブを作成することもできます。 詳細については、次を参照してください。[カスタム T4 テキスト テンプレート ディレクティブ プロセッサの作成](../modeling/creating-custom-t4-text-template-directive-processors.md) Visualization and Modeling SDK を使用してドメイン固有言語 (DSL) を作成すると、DSL の一部としてディレクティブ プロセッサが生成されます。