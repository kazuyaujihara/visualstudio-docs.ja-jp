---
title: CA1715:識別子は正しいプレフィックスを含んでいなければなりません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1715
- IdentifiersShouldHaveCorrectPrefix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectPrefix
- CA1715
ms.assetid: cf45f8df-6855-4cb6-a4e2-7cfed714cf2f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: b794eb7c7a258a843763b2c68902000031c17eb3
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57873605"
---
# <a name="ca1715-identifiers-should-have-correct-prefix"></a>CA1715:識別子は正しいプレフィックスを含んでいなければなりません

|||
|-|-|
|TypeName|IdentifiersShouldHaveCorrectPrefix|
|CheckId|CA1715|
|Category|Microsoft.Naming|
|互換性に影響する変更点|– インターフェイスで発生した場合。<br /><br /> 改行のジェネリック型パラメーターで発生したときにします。|

## <a name="cause"></a>原因

インターフェイスの名前の先頭が大文字の 'I' でありません。

- または -

名前、[ジェネリック型パラメーター](/dotnet/csharp/programming-guide/generics/generic-type-parameters)型またはメソッドに値で始まらない大文字 ' T '。

既定では、このルールのみが検索で外部から参照できるインターフェイス、型、およびメソッドが、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

慣例により、特定のプログラミング要素の名前は固有のプレフィックスで開始します。

インターフェイス名は、大文字、もう 1 つの大文字が続く 'I' で始める必要があります。 このルールは、'MyInterface' や 'IsolatedInterface' などのインターフェイス名の違反を報告します。

ジェネリック型パラメーターの名前が大文字で始まる、' T ' 必要に応じて、もう 1 つの大文字が続く可能性があります。 このルールは、'V' と 'Type' などのジェネリック型パラメーターの名前の違反を報告します。

名前付け規則では、共通言語ランタイムをターゲットとするライブラリの統一的な名前の付け方が規定されています。 これにより、新しいソフトウェア ライブラリを習得するまでの時間を短縮でき、マネージド コード開発の専門家によってライブラリが開発されたという信頼を顧客に与えることができます。

## <a name="configurability"></a>構成機能

このルールからを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、このルールを分析し、コードのどの部分を構成することができます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

### <a name="single-character-type-parameters"></a>単一の文字の型パラメーター

1 文字の型パラメーターをこの規則から除外するかどうかを構成することができます。 たとえば、ことを指定するこのルール*しないで*1 文字の型パラメーターを分析、次のキー/値ペアのいずれかをプロジェクト内の .editorconfig ファイルに追加。

```
# Package version 2.9.0 and later
dotnet_code_quality.CA1715.exclude_single_letter_type_parameters = true

# Package version 2.6.3 and earlier
dotnet_code_quality.CA2007.allow_single_letter_type_parameters = true
```

> [!NOTE]
> このルールは、という名前の型パラメーターのことはありませんが発生した`T`、たとえば、`Collection<T>`します。

### <a name="api-surface"></a>API サーフェス

のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づいています。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1715.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (名前付け) で構成できます。

## <a name="how-to-fix-violations"></a>違反の修正方法

識別子の名前を変更して、プレフィックスが正しくようにします。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告は抑制しないでください。

## <a name="interface-naming-example"></a>インターフェイスの名前付けの例

次のコード スニペットは、不適切な名前のインターフェイスを示しています。

[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_1.cpp)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_1.vb)]
[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_1.cs)]

次のコード スニペットは、'I' とインターフェイスを付けることで、前の違反を修正します。

[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_2.cs)]
[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_2.cpp)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_2.vb)]

## <a name="type-parameter-naming-example"></a>型パラメーター名の例

次のコード スニペットは、不適切な名前のジェネリック型パラメーターを示しています。

[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_3.cpp)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_3.vb)]
[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_3.cs)]

次のコード スニペットは、' T のジェネリック型パラメーターを付けることで以前の違反を修正 '。

[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_4.cpp)]
[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_4.cs)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_4.vb)]

## <a name="related-rules"></a>関連するルール

- [CA1722:識別子には、不適切なプレフィックスはありません。](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)