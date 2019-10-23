---
title: 従来の言語サービスパーサーとスキャナー |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- parsers, language services [managed package framework]
- language services [managed package framework], Parsers
ms.assetid: 1ac3de27-a23b-438d-9593-389e45839cfa
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 11b172fee8f6f5cf1c80d306a8a8b154f7316bf8
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72726738"
---
# <a name="legacy-language-service-parser-and-scanner"></a>従来の言語サービスのパーサーとスキャナー
パーサーは言語サービスの中核です。 Managed Package Framework (MPF) 言語クラスでは、表示されているコードに関する情報を選択する言語パーサーが必要です。 パーサーはテキストを字句トークンに分割し、型と機能によってそれらのトークンを識別します。

## <a name="discussion"></a>ディスカッション
 メソッドをC#次に示します。

```csharp
namespace MyNamespace
{
    class MyClass
    {
        public void MyFunction(int arg1)
        {
            int var1 = arg1;
        }
    }
}
```

 この例では、トークンは単語と句読点です。 トークンの種類は次のとおりです。

|トークン名|トークン型|
|----------------|----------------|
|namespace、class、public、void、int|keyword|
|=|operator|
|{ } ( ) ;|区切り記号|
|MyNamespace、MyClass、MyFunction、arg1、var1|identifier|
|MyNamespace|名前空間|
|MyClass|クラス|
|MyFunction|メソッド|
|arg1|パラメーター|
|var1|ローカル変数|

 パーサーの役割は、トークンを識別することです。 トークンによっては、複数の型を持つことができます。 パーサーによってトークンが識別された後、言語サービスでは、構文の強調表示、かっこの一致、IntelliSense 操作などの有用な機能を提供するために情報を使用できます。

## <a name="types-of-parsers"></a>パーサーの種類
 言語サービスパーサーは、コンパイラの一部として使用されるパーサーと同じではありません。 ただし、この種のパーサーでは、コンパイラパーサーと同じ方法でスキャナーとパーサーの両方を使用する必要があります。

- スキャナーは、トークンの種類を識別するために使用されます。 この情報は、構文の強調表示に使用され、他の操作をトリガーする可能性のあるトークンの種類をすばやく識別します。たとえば、中かっこの照合です。 このスキャナーは、<xref:Microsoft.VisualStudio.Package.IScanner> インターフェイスによって表されます。

- パーサーは、トークンの機能とスコープを記述するために使用されます。 この情報は、メソッド、変数、パラメーター、宣言などの言語要素を識別したり、コンテキストに基づいてメンバーとメソッドシグネチャのリストを提供したりするために、IntelliSense 操作で使用されます。 このパーサーは、中かっこやかっこなど、一致する言語要素のペアを検索するためにも使用されます。 このパーサーには、<xref:Microsoft.VisualStudio.Package.LanguageService> クラスの <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> メソッドを使用してアクセスします。

  言語サービスに対してスキャナーとパーサーを実装する方法は、お客様によって設定されます。 パーサーの動作と独自のパーサーの記述方法を説明するいくつかのリソースが用意されています。 また、パーサーの作成に役立つ、いくつかの無料および商用の製品が用意されています。

### <a name="the-parsesource-parser"></a>ParseSource パーサー
 コンパイラの一部として使用されるパーサー (トークンがなんらかの形式の実行可能コードに変換される) とは異なり、言語サービスパーサーはさまざまな理由やさまざまなコンテキストで呼び出すことができます。 @No__t_1 クラスの <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> メソッドにこの方法を実装する方法はお勧めします。 @No__t_0 メソッドがバックグラウンドスレッドで呼び出される可能性があることに注意してください。

> [!CAUTION]
> @No__t_0 構造体には、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> オブジェクトへの参照が含まれています。 この <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> オブジェクトをバックグラウンドスレッドで使用することはできません。 実際、基本 MPF クラスの多くをバックグラウンドスレッドで使用することはできません。 これには、<xref:Microsoft.VisualStudio.Package.Source>、<xref:Microsoft.VisualStudio.Package.ViewFilter>、<xref:Microsoft.VisualStudio.Package.CodeWindowManager> クラス、およびビューと直接または間接的に通信するその他のクラスが含まれます。

 このパーサーは、通常、最初に呼び出されたとき、または <xref:Microsoft.VisualStudio.Package.ParseReason> の解析理由の値が指定されたときに、ソースファイル全体を解析します。 後続の <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> メソッドの呼び出しでは、解析されたコードの一部を処理します。前の完全解析操作の結果を使用して、より短時間で実行できます。 @No__t_0 メソッドは、解析操作の結果を <xref:Microsoft.VisualStudio.Package.AuthoringSink> オブジェクトと <xref:Microsoft.VisualStudio.Package.AuthoringScope> オブジェクトを介して通信します。 @No__t_0 オブジェクトは、特定の解析の理由についての情報を収集するために使用されます。たとえば、パラメーターリストを持つ一致する中かっこまたはメソッドのシグネチャの範囲に関する情報などです。 @No__t_0 には、宣言とメソッドシグネチャのコレクションが用意されています。また、高度な編集 オプション (**定義へ**、**宣言へ**、**参照へジャンプ**) もサポートされています。

### <a name="the-iscanner-scanner"></a>IScanner スキャナー
 @No__t_0 を実装するスキャナーも実装する必要があります。 ただし、このスキャナーは <xref:Microsoft.VisualStudio.Package.Colorizer> クラスによって1行ずつ実行されるため、通常は実装が簡単です。 各行の先頭で、MPF は <xref:Microsoft.VisualStudio.Package.Colorizer> クラスに、スキャナーに渡される状態変数として使用する値を与えます。 各行の最後で、更新された状態変数がスキャナーから返されます。 MPF は各行のこの状態情報をキャッシュするため、スキャナーは、ソースファイルの先頭から開始することなく、任意の行から解析を開始できます。 この1行の高速スキャンにより、エディターはユーザーに迅速なフィードバックを提供できます。

## <a name="parsing-for-matching-braces"></a>一致する中かっこの解析
 この例は、ユーザーが入力した右中かっこと照合するための制御フローを示しています。 このプロセスでは、色付けに使用されるスキャナーを使用して、トークンの種類と、トークンが対応する中かっこの操作をトリガーできるかどうかを判断します。 トリガーが見つかった場合は、<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> メソッドが呼び出され、対応する中かっこが検索されます。 最後に、2つの中かっこが強調表示されます。

 トリガーの名前と解析の理由で中かっこが使用されている場合でも、このプロセスは実際の中かっこに限定されません。 一致するペアとして指定されている文字のペアはすべてサポートされています。 例として、(と)、\< と >、および [and] があります。

 言語サービスでは、対応する中かっこがサポートされているものとします。

1. ユーザーは、右中かっこ (}) を入力します。

2. 中かっこは、ソースファイルのカーソル位置に挿入され、カーソルは1つ進められます。

3. @No__t_1 クラスの <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> メソッドは、型指定された右中かっこを使用して呼び出されます。

4. @No__t_0 メソッドは <xref:Microsoft.VisualStudio.Package.Source> クラスの <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> メソッドを呼び出して、現在のカーソル位置の直前の位置にあるトークンを取得します。 このトークンは、型指定された右中かっこに対応します)。

    1. @No__t_0 メソッドは、<xref:Microsoft.VisualStudio.Package.Colorizer> オブジェクトの <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> メソッドを呼び出して、現在の行のすべてのトークンを取得します。

    2. @No__t_0 メソッドは、現在の行のテキストを使用して、<xref:Microsoft.VisualStudio.Package.IScanner> オブジェクトの <xref:Microsoft.VisualStudio.Package.IScanner.SetSource%2A> メソッドを呼び出します。

    3. @No__t_0 メソッドは、<xref:Microsoft.VisualStudio.Package.IScanner> オブジェクトの <xref:Microsoft.VisualStudio.Package.IScanner.ScanTokenAndProvideInfoAboutIt%2A> メソッドを繰り返し呼び出して、現在の行からすべてのトークンを収集します。

    4. @No__t_0 メソッドは、<xref:Microsoft.VisualStudio.Package.Source> クラスのプライベートメソッドを呼び出して、目的の位置を含むトークンを取得し、<xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> メソッドから取得したトークンのリストを渡します。

5. @No__t_0 メソッドは、<xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> メソッドから返されたトークンで <xref:Microsoft.VisualStudio.Package.TokenTriggers> のトークントリガーフラグを検索します。つまり、右中かっこを表すトークンです。

6. @No__t_0 のトリガーフラグが見つかった場合は、<xref:Microsoft.VisualStudio.Package.Source> クラスの <xref:Microsoft.VisualStudio.Package.Source.MatchBraces%2A> メソッドが呼び出されます。

7. @No__t_0 メソッドは、解析の理由値が <xref:Microsoft.VisualStudio.Package.ParseReason> の解析操作を開始します。 この操作では、最終的に <xref:Microsoft.VisualStudio.Package.LanguageService> クラスの <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> メソッドを呼び出します。 非同期解析が有効になっている場合、<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> メソッドへのこの呼び出しはバックグラウンドスレッドで発生します。

8. 解析操作が完了すると、`HandleMatchBracesResponse` という内部完了ハンドラー (コールバックメソッドとも呼ばれます) が <xref:Microsoft.VisualStudio.Package.Source> クラスで呼び出されます。 この呼び出しは、パーサーによってではなく、<xref:Microsoft.VisualStudio.Package.LanguageService> 基底クラスによって自動的に行われます。

9. @No__t_0 メソッドは、<xref:Microsoft.VisualStudio.Package.ParseRequest> オブジェクトに格納されている <xref:Microsoft.VisualStudio.Package.AuthoringSink> オブジェクトから範囲のリストを取得します。 (スパンは、ソースファイル内の行と文字の範囲を指定する <xref:Microsoft.VisualStudio.TextManager.Interop.TextSpan> 構造体です)。この範囲の一覧には、通常、左中かっこと終わりかっこの2つの範囲が含まれています。

10. @No__t_0 メソッドは、<xref:Microsoft.VisualStudio.Package.ParseRequest> オブジェクトに格納されている <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> オブジェクトの <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A> メソッドを呼び出します。 これにより、指定された範囲が強調表示されます。

11. @No__t_0 プロパティ <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A> が有効になっている場合、`HandleBracesResponse` メソッドは、一致するスパンに含まれるテキストを取得し、そのスパンの最初の80文字をステータスバーに表示します。 これは、<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> メソッドに、一致するペアに付随する言語要素が含まれている場合に最適です。 詳細については、<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A> プロパティを参照してください。

12. 完成です。

### <a name="summary"></a>まとめ
 通常、対応する中かっこの演算は、単純な言語要素のペアに限定されます。 一致する3要素 ("`if(...)`"、"`{`"、"`}`"、"`else`"、"`{`"、"`}`" など) など、より複雑な要素を、単語入力操作の一部として強調表示することができます。 たとえば、"else" という単語が終了した場合、一致する "`if`" ステートメントを強調表示できます。 一連の `if` / `else if` ステートメントがある場合は、対応するかっこと同じメカニズムを使用して、すべてのステートメントを強調表示できます。 @No__t_0 の基本クラスでは、次のように、この機能が既にサポートされています。スキャナーは、トークントリガーの値を返す必要があります。また、トリガー値は、カーソル位置の前にあるトークンの <xref:Microsoft.VisualStudio.Package.TokenTriggers> を <xref:Microsoft.VisualStudio.Package.TokenTriggers> ます。

 詳細については、「[従来の言語サービスでの中かっこの一致](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)」を参照してください。

## <a name="parsing-for-colorization"></a>色付けの解析
 色分けソースコードは簡単です。トークンの種類を特定し、その型に関する色情報を返すだけです。 @No__t_0 クラスは、エディターとスキャナー間の仲介役として機能し、すべてのトークンに関する色情報を提供します。 @No__t_0 クラスは、<xref:Microsoft.VisualStudio.Package.IScanner> オブジェクトを使用して、行を色分けしたり、ソースファイル内のすべての行の状態情報を収集したりします。 MPF 言語サービスクラスでは、<xref:Microsoft.VisualStudio.Package.Colorizer> クラスは、<xref:Microsoft.VisualStudio.Package.IScanner> インターフェイスを介してのみスキャナーと通信するため、オーバーライドする必要はありません。 @No__t_0 インターフェイスを実装するオブジェクトを指定するには、<xref:Microsoft.VisualStudio.Package.LanguageService> クラスの <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> メソッドをオーバーライドします。

 @No__t_0 スキャナーには、<xref:Microsoft.VisualStudio.Package.IScanner.SetSource%2A> メソッドを使用してソースコードの行が指定されています。 @No__t_0 メソッドの呼び出しは、行がトークンを使い果たすまで行の次のトークンを取得するために繰り返されます。 色付けの場合、MPF はすべてのソースコードを行のシーケンスとして扱います。 そのため、スキャナーは、ソースを行として扱うことができる必要があります。 また、任意の行をいつでもスキャナーに渡すことができ、保証されるのは、スキャナーがスキャン対象の行の前の状態変数を受け取ることだけです。

 @No__t_0 クラスは、トークントリガーを識別するためにも使用されます。 これらのトリガーは、特定のトークンが単語の補完や対応する中かっこなどのより複雑な操作を開始できることを MPF に伝えます。 このようなトリガーは高速である必要があり、任意の場所に配置する必要があるため、スキャナーはこのタスクに最適です。

 詳細については、「[従来の言語サービスの構文色分け](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)」を参照してください。

## <a name="parsing-for-functionality-and-scope"></a>機能とスコープの解析
 機能とスコープの解析には、発生したトークンの種類を特定するだけではなく、より多くの労力が必要になります。 パーサーは、トークンの種類だけでなく、トークンを使用する機能も識別する必要があります。 たとえば、識別子は単なる名前ですが、お使いの言語では、コンテキストに応じて、クラス、名前空間、メソッド、または変数の名前を識別子として使用できます。 トークンの一般的な型は識別子である場合がありますが、識別子の内容や定義されている場所によっては、識別子に他の意味がある場合もあります。 この id を設定するには、解析対象の言語についての豊富な知識をパーサーに追加する必要があります。 ここで <xref:Microsoft.VisualStudio.Package.AuthoringSink> クラスを示します。 @No__t_0 クラスは、識別子、メソッド、一致する言語のペア (中かっこやかっこなど)、および言語3要素 ("`foreach()`"、"`{`"、"`}`" など、3つの部分がある点を除き、言語のペアに似ています) に関する情報を収集します. さらに、<xref:Microsoft.VisualStudio.Package.AuthoringSink> クラスをオーバーライドしてコード id をサポートすることもできます。これは、デバッガーを読み込む必要がないように、ブレークポイントの初期検証で使用されます。また、ローカル変数とパラメーターを表示する [**自動**変数デバッグ] ウィンドウが使用されます。プログラムがデバッグされているときは自動的に、デバッガーによって表示されるものに加えて、適切なローカル変数とパラメーターをパーサーが識別する必要があります。

 @No__t_0 オブジェクトは、<xref:Microsoft.VisualStudio.Package.ParseRequest> オブジェクトの一部としてパーサーに渡され、新しい <xref:Microsoft.VisualStudio.Package.ParseRequest> オブジェクトが作成されるたびに新しい <xref:Microsoft.VisualStudio.Package.AuthoringSink> オブジェクトが作成されます。 また、<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> メソッドは、さまざまな IntelliSense 操作を処理するために使用される <xref:Microsoft.VisualStudio.Package.AuthoringScope> オブジェクトを返す必要があります。 @No__t_0 オブジェクトは、解析の理由に応じて、宣言の一覧とメソッドのリストを保持します。これらのメソッドのいずれかに設定されます。 @No__t_0 クラスを実装する必要があります。

## <a name="see-also"></a>関連項目
- [従来の言語サービスの実装](../../extensibility/internals/implementing-a-legacy-language-service1.md)
- [従来の言語サービスの概要](../../extensibility/internals/legacy-language-service-overview.md)
- [従来の言語サービスでの構文の配色変更](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)
- [従来の言語サービスでのかっこの一致](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)