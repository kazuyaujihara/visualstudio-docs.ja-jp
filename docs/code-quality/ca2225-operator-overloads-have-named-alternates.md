---
title: CA2225:演算子オーバーロードには名前付けされた代替が存在します
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
helpviewer_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
ms.assetid: af8f7ab1-63ad-4861-afb9-b7a7a2be15e1
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2f427bcdf4ec4e88dcc2842699d738dae7e8e09d
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69546907"
---
# <a name="ca2225-operator-overloads-have-named-alternates"></a>CA2225:演算子オーバーロードには名前付けされた代替が存在します

|||
|-|-|
|TypeName|OperatorOverloadsHaveNamedAlternates|
|CheckId|CA2225|
|Category|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

演算子のオーバーロードが検出されましたが、予期された名前の別のメソッドが見つかりませんでした。

既定では、この規則は外部から参照できる型のみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

演算子のオーバーロードでは、型の計算を表すためにシンボルを使用できます。 たとえば、追加のためにプラス記号 (+) をオーバーロードする型には、通常、"Add" という名前の代替メンバーがあります。 名前付き代替メンバーは、演算子と同じ機能へのアクセスを提供し、オーバーロードされた演算子をサポートしない言語でプログラミングする開発者向けに用意されています。

このルールは、次の表に示す演算子を検証します。

|C#|Visual Basic|C++|代替名|
|---------|------------------|-----------|--------------------|
|+ (バイナリ)|+|+ (バイナリ)|追加|
|+=|+=|+=|追加|
|&|と|&|BitwiseAnd|
|&=|および =|&=|BitwiseAnd|
|&#124;|または|&#124;|BitwiseOr|
|&#124;=|または =|&#124;=|BitwiseOr|
|--|N/A|--|Decrement|
|/|/|/|除算|
|/=|/=|/=|除算|
|==|=|==|Equals|
|^|Xor|^|Xor|
|^=|Xor =|^=|Xor|
|>|>|>|比較|
|>=|>=|>=|比較|
|++|N/A|++|インクリメント|
|<>|!=|Equals|
|<<|<<|<<|から左へ|
|<<=|<<=|<<=|から左へ|
|<|<|<|比較|
|<=|<=|\<=|比較|
|&&|N/A|&&|LogicalAnd|
|&#124;&#124;|N/A|&#124;&#124;|LogicalOr|
|!|N/A|!|LogicalNot|
|%|Mod|%|Mod または剰余|
|%=|N/A|%=|Mod|
|* (バイナリ)|*|*|乗算|
|*=|N/A|*=|乗算|
|~|Not|~|OnesComplement|
|>>|>>|>>|プロパティながら|
=|N/A|>>=|プロパティながら|
|-(バイナリ)|-(バイナリ)|-(バイナリ)|減算|
|-=|N/A|-=|減算|
|true|IsTrue|N/A|IsTrue (プロパティ)|
|-(単項)|N/A|-|無効|
|+ (単項)|N/A|+|Plus|
|False|IsFalse|False|IsTrue (プロパティ)|

選択した言語では、N/A = = をオーバーロードすることはできません。

また、およびと`SomeType` `FromSomeType`いう名前`ToSomeType`のメソッドがあるかどうかをチェックすることにより、型 () の暗黙的なキャスト演算子と明示的なキャスト演算子も確認します。

でC#は、二項演算子がオーバーロードされると、対応する代入演算子 (存在する場合) も暗黙的にオーバーロードされます。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、演算子に対して別の方法を実装します。推奨される代替名を使用して名前を指定します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

共有ライブラリを実装している場合は、この規則による警告を抑制しないでください。 アプリケーションは、このルールの警告を無視できます。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca2225.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (使用状況) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="example"></a>例

次の例では、この規則に違反する構造体を定義しています。 この例を修正するには、 `Add(int x, int y)`パブリックメソッドを構造体に追加します。

[!code-csharp[FxCop.Usage.OperatorOverloadsHaveNamedAlternates#1](../code-quality/codesnippet/CSharp/ca2225-operator-overloads-have-named-alternates_1.cs)]

## <a name="related-rules"></a>関連するルール

- [CA1046参照型の演算子 equals をオーバーロードしない](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)
- [CA2226演算子には対称的なオーバーロードが必要です](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)
- [CA2224オーバーロードする演算子 equals で equals をオーバーライドします](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2218オーバーライドする Equals で GetHashCode をオーバーライドします](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)
- [CA2231: ValueType.Equals のオーバーライドで、演算子 equals をオーバーロードします](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)