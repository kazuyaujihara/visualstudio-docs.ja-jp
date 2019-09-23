---
title: パフォーマンスに関する警告
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.performancerules
helpviewer_keywords:
- warnings, performance
- performance warnings
- performance, warnings
- managed code analysis warnings, performance warnings
ms.assetid: e014ac3a-02e6-46d9-942c-3491dd63782f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f8d8f06fe0d3d1e114662a8ea99d1458d65e3e4c
ms.sourcegitcommit: 541a0556958201ad6626bc8638406ad02640f764
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "71079246"
---
# <a name="performance-warnings"></a>パフォーマンスに関する警告
パフォーマンスの警告は、高パフォーマンスのライブラリとアプリケーションをサポートします。

## <a name="in-this-section"></a>このセクションの内容

| ルール | 説明 |
| - | - |
| [CA1800不必要にキャストしない](../code-quality/ca1800-do-not-cast-unnecessarily.md) | 二重のキャストがあるとパフォーマンスが低下します。特に、小さな繰り返しステートメントでキャストが実行される場合はそうです。 |
| [CA1801使用されていないパラメーターの確認](../code-quality/ca1801-review-unused-parameters.md) | メソッドのシグネチャに、メソッドの本体で使用されていないパラメーターがあります。 |
| [CA1802適切な場所にリテラルを使用する](../code-quality/ca1802-use-literals-where-appropriate.md) | フィールドは静的および読み取り専用 (で[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]は Shared および ReadOnly) として宣言され、コンパイル時に計算できるという値を使用して初期化されます。 対象フィールドに割り当てられている値は、コンパイル時に計算であるため、宣言を const に変更 (で Const [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) の代わりに実行時のコンパイル時に値を計算するためのフィールドします。 |
| [CA1804未使用のローカルの削除](../code-quality/ca1804-remove-unused-locals.md) | 使用されていないローカル変数や不要な引数があると、アセンブリのサイズが大きくなり、パフォーマンスが低下します。 |
| [CA1806メソッドの結果を無視しない](../code-quality/ca1806-do-not-ignore-method-results.md) | 新しいオブジェクトが作成されましたが、使用されていないか、新しい文字列を作成して返すメソッドが呼び出され、新しい文字列が使用されていないか、またはコンポーネントオブジェクトモデル (COM) または P/Invoke メソッドが、使用されていない HRESULT またはエラーコードを返しています。 |
| [CA1809過度なローカルを避ける](../code-quality/ca1809-avoid-excessive-locals.md) | パフォーマンス最適化の一般的な方法として、メモリではなくプロセッサのレジスタに値を格納する方法があります。これは "値のレジスタ格納" と呼ばれます。  すべてのローカル変数は、レジスタである可能性を向上させるのには、64 をローカル変数の数を制限します。 |
| [CA1810参照型の静的フィールドをインラインで初期化します](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md) | 型で明示的な静的コンストラクターを宣言すると、Just-In-Time (JIT) コンパイラが、静的コンストラクターが呼び出されたことを確認するために、型の静的メソッドと静的インスタンス コンストラクターに個別にチェックを追加します。 静的コンストラクターのチェックによってパフォーマンスが低下することがあります。 |
| [CA1811呼び出されるプライベートコードを避ける](../code-quality/ca1811-avoid-uncalled-private-code.md) | プライベートまたは内部 (アセンブリレベル) のメンバーは、アセンブリ内の呼び出し元を持っていません。また、共通言語ランタイムによって呼び出されず、デリゲートによって呼び出されません。 |
| [CA1812インスタンス内部クラスを回避する](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md) | アセンブリ レベルの型のインスタンスが、アセンブリ内のコードから作成されません。 |
| [CA1813:封印されていない属性を避ける](../code-quality/ca1813-avoid-unsealed-attributes.md) | .NET には、カスタム属性を取得するためのメソッドが用意されています。 既定では、これらのメソッドで属性の継承階層が検索されます。 属性をシールすると、継承階層の全体が検索されなくなるため、パフォーマンスが向上します。 |
| [CA1814多次元配列よりもジャグ配列を優先する](../code-quality/ca1814-prefer-jagged-arrays-over-multidimensional.md) | ジャグ配列とは、その要素も配列である配列です。 要素を構成する配列のサイズは異なる可能性があるため、一部のデータセットで無駄な領域が生じる可能性があります。 |
| [CA1815equals および operator equals を値型でオーバーライドします](../code-quality/ca1815-override-equals-and-operator-equals-on-value-types.md)」を参照してください。 | 値型の場合、Equals を継承した実装が Reflection ライブラリを使用して、すべてのフィールドの内容を比較します。 Reflection は計算コストが高いため、場合によってはすべてのフィールドで等値性を比較する必要はありません。 ユーザーがインスタンスの比較または並べ替えを行うことや、ハッシュ テーブル キーとしてインスタンスを使用することが予想される場合には、値型に Equals を実装する必要があります。 |
| [CA1816GC を呼び出します。Gc.suppressfinalize](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md) | Dispose の実装であるメソッドは、GC を呼び出しません。Gc.suppressfinalize、または Dispose の実装ではないメソッドは GC を呼び出します。Gc.suppressfinalize、またはメソッドは GC を呼び出します。Gc.suppressfinalize は、この (では[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]Me) 以外のものを渡します。 |
| [CA1819プロパティは配列を返すことはできません](../code-quality/ca1819-properties-should-not-return-arrays.md) | プロパティが読み取り専用の場合でも、プロパティによって返される配列は書き込み禁止になりません。 配列の改ざんを防ぐには、プロパティで配列のコピーを返す必要があります。 一般に、このようなプロパティを呼び出すときのパフォーマンス低下は理解されません。 |
| [CA1820文字列の長さを使用して空の文字列をテストする](../code-quality/ca1820-test-for-empty-strings-using-string-length.md) | String.Length プロパティまたは String.IsNullOrEmpty メソッドを使用して文字列を比較する方法は、Equals を使用する場合よりもはるかに高速です。 |
| [CA1821: 空のファイナライザーを削除します](../code-quality/ca1821-remove-empty-finalizers.md) | オブジェクトの有効期間の追跡に関連するパフォーマンス オーバーヘッドが増大するため、ファイナライザーは可能な限り使用しないでください。 空のファイナライザーを使用すると、追加のオーバーヘッドが発生します。 |
| [CA1822メンバーを静的としてマーク](../code-quality/ca1822-mark-members-as-static.md) | インスタンス データにアクセスしない、またはインスタンス メソッドを呼び出さないメンバーは、静的 ([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] では共有) としてマークできます。 メソッドを静的としてマークすると、コンパイラはこれらのメンバーに対する非仮想呼び出しサイトを出力します。 パフォーマンス重視のコードでは、これにより大きくパフォーマンスを向上できます。 |
| [CA1823使用されていないプライベートフィールドを避ける](../code-quality/ca1823-avoid-unused-private-fields.md) | アセンブリ内でアクセスされていないと思われるプライベート フィールドが検出されました。 |
| [CA1824アセンブリを NeutralResourcesLanguageAttribute にマークします](../code-quality/ca1824-mark-assemblies-with-neutralresourceslanguageattribute.md) | NeutralResourcesLanguage 属性は、ResourceManager に対し、アセンブリのニュートラル カルチャのリソースを表示するために使用した言語を通知します。 これにより、読み込んだ最初のリソースに対する検索のパフォーマンスが向上し、ワーキング セットを縮小できます。 |
| [CA1825:長さ0の配列割り当てを回避する](../code-quality/ca1825.md) | 長さ0の配列を初期化すると、不要なメモリ割り当てにつながります。 代わりに、を呼び出す<xref:System.Array.Empty%2A?displayProperty=nameWithType>ことによって、静的に割り当てられた空の配列インスタンスを使用します。 メモリ割り当ては、このメソッドのすべての呼び出しで共有されます。 |
