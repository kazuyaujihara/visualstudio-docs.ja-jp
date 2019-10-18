---
title: グローバリゼーションの警告
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.globalizationrules
helpviewer_keywords:
- warnings, globalization
- globalization warnings
- globalization [Visual Studio], warnings
- managed code analysis warnings, globalization warnings
ms.assetid: a8d12d41-14bf-4b43-af24-168312d7c390
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 264f94a537bc9c067a2f0016115a4cc1bd387fb8
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72449008"
---
# <a name="globalization-warnings"></a>グローバリゼーションの警告
グローバリゼーションの警告は、国際対応のライブラリとアプリケーションをサポートします。

## <a name="in-this-section"></a>このセクションの内容

|規則|説明|
|----------|-----------------|
|[CA1300: MessageBoxOption を指定します](../code-quality/ca1300-specify-messageboxoptions.md)|テキストを右から左へ読むカルチャでメッセージ ボックスを正しく表示するには、MessageBoxOptions 列挙体の RightAlign メンバーと RtlReading メンバーを、Show メソッドに渡す必要があります。|
|[CA1301: アクセラレータが重複しないようにします](../code-quality/ca1301-avoid-duplicate-accelerators.md)|Alt キーを使用するアクセス キー (アクセラレータとも呼ばれます) によって、キーボードからコントロールにアクセスできます。 複数のコントロールが重複するアクセスキーを持っている場合、アクセスキーの動作は適切に定義されていません。|
|[CA1302: ロケール特有の文字列をハードコードしません](../code-quality/ca1302-do-not-hardcode-locale-specific-strings.md)|System.Environment.SpecialFolder 列挙体には、特殊なシステム フォルダーを参照するメンバーが含まれます。 このフォルダーの位置は、オペレーティング システムによって異なる場合、ユーザーが位置を変更する場合、および位置がローカライズされる場合があります。 System.environment.specialfolder 列挙型に関連付けられている場所は、GetFolderPath メソッドによって返されます。これは、現在実行中のコンピューターに適しています。|
|[CA1303: ローカライズされたパラメーターとしてリテラルを渡さないでください](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)|外部から参照できるメソッドは、.NET コンストラクターまたはメソッドにパラメーターとして文字列リテラルを渡し、その文字列はローカライズ可能である必要があります。|
|[CA1304: CultureInfo を指定します](../code-quality/ca1304-specify-cultureinfo.md)|System.Globalization.CultureInfo パラメーターを受け入れるオーバーロードを持つメンバーを呼び出しているメソッドまたはコンストラクターが、CultureInfo パラメーターを使用するオーバーロードを呼び出していません。 CultureInfo オブジェクトまたは System.IFormatProvider オブジェクトが指定されない場合、オーバーロードされたメンバーから提示された既定値は、すべてのロケールに効果が及ばない可能性があります。|
|[CA1305: IFormatProvider を指定します](../code-quality/ca1305-specify-iformatprovider.md)|System.IFormatProvider パラメーターを受け入れるオーバーロードを持つメンバーを 1 つ以上呼び出しているメソッドまたはコンストラクターが、IFormatProvider パラメーターを使用するオーバーロードを呼び出していません。 System.Globalization.CultureInfo オブジェクトまたは IFormatProvider オブジェクトが指定されない場合、オーバーロードされたメンバーから提示された既定値は、すべてのロケールに効果が及ばない可能性があります。|
|[CA1306: データ型のロケールを設定します](../code-quality/ca1306-set-locale-for-data-types.md)|ロケールによって、データに関するカルチャ固有の表示要素が決まります。たとえば、数値、通貨記号、並べ替え順序に使用する形式などです。 DataTable または DataSet を作成するときは、ロケールを明示的に設定する必要があります。|
|[CA1307: StringComparison の指定](../code-quality/ca1307-specify-stringcomparison.md)|文字列比較演算で、StringComparison パラメーターを設定しないメソッド オーバーロードが使用されています。|
|[CA1308: 文字列を大文字に標準化します](../code-quality/ca1308-normalize-strings-to-uppercase.md)|文字列は大文字に正規化する必要があります。 小文字への変換時に 1 つの小さい文字グループをラウンド トリップさせることができません。|
|[CA1309: 順序を示す StringComparison を使用します](../code-quality/ca1309-use-ordinal-stringcomparison.md)|非言語的な文字列比較演算で、StringComparison パラメーターが Ordinal または OrdinalIgnoreCase に設定されていません。 パラメーターを StringComparison.Ordinal または StringComparison.OrdinalIgnoreCase に明示的に設定することによって、多くの場合、コードの速度、正確さ、および信頼性が向上します。|
|[CA2101: P/Invoke 文字列引数に対してマーシャリングを指定します](../code-quality/ca2101.md)|プラットフォーム呼び出しメンバーは、部分的に信頼された呼び出し元を許可し、文字列パラメーターを持ち、文字列を明示的にマーシャリングしません。 これはセキュリティ上の脆弱性となる可能性があります。|
