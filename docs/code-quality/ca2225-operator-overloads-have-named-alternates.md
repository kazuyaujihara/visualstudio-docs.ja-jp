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
ms.openlocfilehash: a8a1c7015421b686d47bfea4c3341ec76748f8ad
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806616"
---
# <a name="ca2225-operator-overloads-have-named-alternates"></a>CA2225:演算子オーバーロードには名前付けされた代替が存在します

|||
|-|-|
|TypeName|OperatorOverloadsHaveNamedAlternates|
|CheckId|CA2225|
|Category|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

演算子のオーバー ロードが検出され、予期される名前付きの代替方法が見つかりませんでした。

既定では、このルールのみが検索に、外部から参照の種類が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

演算子のオーバー ロードでは、型の計算を表すシンボルを使用できるようにします。 たとえば、追加するプラス記号 (+) をオーバー ロードする型は 'Add' という名前の代替メンバーを通常があります。 名前付きの代替メンバーは、演算子と同じ機能にアクセスできるようにおり、オーバー ロードされた演算子をサポートしない言語でプログラミングする開発者向け提供されます。

このルールは、次の表に示す演算子を調べます。

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
|<<|<<|<<|プロパティ|
|<<=|<<=|<<=|プロパティ|
|<|<|<|比較|
|<=|<=|\<=|比較|
|&&|N/A|&&|LogicalAnd|
|&#124;&#124;|N/A|&#124;&#124;|LogicalOr|
|!|N/A|!|LogicalNot|
|%|Mod|%|Mod または残りの部分|
|%=|N/A|%=|Mod|
|* (バイナリ)|*|*|乗算|
|*=|N/A|*=|乗算|
|~|Not|~|OnesComplement|
|>>|>>|>>|プロパティ|
=|N/A|>>=|プロパティ|
|-(バイナリ)|-(バイナリ)|-(バイナリ)|減算|
|-=|N/A|-=|減算|
|true|IsTrue|N/A|IsTrue (プロパティ)|
|-(単項)|N/A|-|負数化します。|
|+ (単項)|N/A|+|プラス|
|False|IsFalse|False|IsTrue (プロパティ)|

該当なし = =、選択した言語でオーバー ロードすることはできません。

ルールでは、型の明示的および暗黙的なキャスト演算子も確認します (`SomeType`) という名前のメソッドをチェックして`ToSomeType`と`FromSomeType`します。

C# の場合は、二項演算子をオーバー ロードすると、対応する代入演算子、存在する場合も暗黙的にオーバー ロードできます。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するのには、演算子の代替メソッドを実装します。推奨される代替名を使用して名前を付けます。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

共有ライブラリを実装している場合は、この規則による警告を抑制しないでください。 アプリケーションでは、この規則による警告を無視できます。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca2225.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (使用) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="example"></a>例

次の例では、この規則に違反する構造体を定義します。 例を修正する追加パブリック`Add(int x, int y)`構造体へのメソッド。

[!code-csharp[FxCop.Usage.OperatorOverloadsHaveNamedAlternates#1](../code-quality/codesnippet/CSharp/ca2225-operator-overloads-have-named-alternates_1.cs)]

## <a name="related-rules"></a>関連するルール

- [CA1046:参照型で、演算子 equals をオーバー ロードしません。](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)
- [CA2226:演算子は対称型オーバー ロードである必要があります。](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)
- [CA2224:オーバー ロードする演算子 equals で equals をオーバーライド](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2218:Equals をオーバーライドの GetHashCode をオーバーライドします。](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)
- [CA2231: ValueType.Equals のオーバーライドで、演算子 equals をオーバーロードします](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)