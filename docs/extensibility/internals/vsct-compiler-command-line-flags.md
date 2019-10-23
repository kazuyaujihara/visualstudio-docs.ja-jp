---
title: VSCT コンパイラのコマンドラインフラグ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, compiling
- command-table file compilation (VSCT files)
ms.assetid: 9dc6c33f-e6cf-4cf2-9b05-e8f7bfac1cfb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 71634a007019dd39e843ccc63af1c3188f778ea9
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72722030"
---
# <a name="vsct-compiler-command-line-flags"></a>VSCT コンパイラのコマンドライン フラグ
Visual Studio コマンドテーブル (VSCT) コンパイラには、vsct ファイルのコンパイルが正常に行われるようにするためのコマンドラインスイッチが用意されています。

## <a name="command-line-parameters"></a>コマンドラインパラメーター
 @No__t_0**コマンド**ウィンドウから基本的な vsct ヘルプを表示するには、 *Visual Studio SDK のインストールパス*\VisualStudioIntegration\Tools\Bin\ フォルダーに移動し、次のように入力します。

```
vsct /?
```

 次の値が返されます。

```
Microsoft (R) Visual Studio (R) Command Table Compiler Version 3.00.2000

Syntax: vsct <infile> [<outfile>] [-S[symbols file]] [-D<preprocessor-define>]*
[-I<include-path>]* [-L<language>] [-E[C|H|N]:<name>]

  -D    Specify any additional preprocessor defines
  -I    Indicate what additional include paths to send to the preprocessor
  -L    Specify the language to use when selecting strings
  -E    Emit C# objects in the specified namespace for command items,
        followed by [L|F|H|N]:<value>
        F = Name of the file to emit (used if -EL is provided)
        L = Name of a language providing a CodeDOM provider
        N = namespace (required if -EL is provided)
        H = C++ header
  -c    Clean build skipping dependency checks
  -v    Verbose output
```

> [!NOTE]
> 文字-(ダッシュ) と/(スラッシュ) はどちらも、コマンドラインパラメーターを示すために使用できます。

 使用可能なフラグとその意味は次のとおりです。

|切り替え|説明|
|------------|-----------------|
|-D|定義されている追加のシンボルを指定します。|
|-I|ファイル参照を解決するときに使用する追加のインクルードパスを指定します。|
|-L|@No__t_0 カルチャ名を指定します (例: "en-us")。|
|-E|コマンドC#項目に対して指定した名前空間のオブジェクトを出力&#124;し&#124;、その後に [c H C#N]: C++ *filename*を出力します。 c =、H = header、N = 名前空間を指定します。 にC#は名前空間が必要です。|
|-v|詳細出力。|

 -L スイッチは、文字列のグループを選択して、指定された <xref:System.Globalization.CultureInfo> カルチャ名に対応するバイナリの cto ファイルを生成するようにコンパイラに指示します。 指定されたカルチャ名は、vsct ファイル内の1つ以上の[文字列要素](../../extensibility/strings-element.md)の言語属性と一致する必要があります。 Strings 要素に言語属性がない場合は、それを含んでいる[Commandtable 要素](../../extensibility/commandtable-element.md)から継承されます。

 Vsct ファイルには、複数の文字列要素を含めることができ、それぞれの言語属性が異なる場合があります。 グローバリゼーションは、VSCT コンパイラを複数回実行し、各カルチャ名の-L スイッチを変更することで実現されます。

 -L スイッチによって指定されたカルチャ名が文字列要素の Language 属性と一致しない場合、コンパイラは地域ではなく、言語との照合を試みます。 たとえば、"en-us" が見つからない場合、コンパイラは代わりに "en" を試行します。 失敗した場合、オペレーティングシステムの現在のカルチャが試行されます。 失敗した場合は、最初に見つかった文字列要素がコンパイルされます。

 -E スイッチを使用すると、コマンドテーブルによって使用されるシンボルを含む C スタイルのヘッダーファイルを生成したり、コマンドシンボルC#のオブジェクトを含むファイルを出力したりできます。

 -D および-I スイッチには、同じ名前を持つ Cl.exe C プリプロセッサフラグの構文があります。 X = Y という形式の-D 定義は `Condition` の属性で > テストの XML ベースの \<Defined の展開に使用されます。 -I インクルードパスを使用して、\<Include >、\<Extern > および \<Bitmap ファイル参照を解決します。 詳細については、「 [Vsct XML スキーマリファレンス](../../extensibility/vsct-xml-schema-reference.md)」を参照してください。

 VSCT コンパイラは、以前にビルドされたバイナリファイルを逆コンパイルすることもできます。 これを行うには、\<infile > にバイナリファイルを指定します。   バイナリファイルが VSCT コンパイラによって生成された場合、そのシンボルは既に埋め込まれており、出力の \<Symbols > セクションにシンボリック名を含む出力が生成されます。 バイナリが CTC コンパイラによって生成された場合、出力には実際の Guid と Id が含まれます。 現在のバージョンの mageui.exe によって生成された * ctsym ファイルがバイナリ入力ファイルと同じフォルダーにある場合、シンボルはそのファイルから読み込まれ、出力に使用されます。

## <a name="see-also"></a>関連項目
- [Visual Studio Command Table (.Vsct) ファイル](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [VSCT XML スキーマ リファレンス](../../extensibility/vsct-xml-schema-reference.md)
- [VSPackage でユーザー インターフェイス要素を追加する方法](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)