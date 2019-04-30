---
title: CA1012:抽象型にはコンストラクターを含めません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- AbstractTypesShouldNotHaveConstructors
- CA1012
helpviewer_keywords:
- CA1012
ms.assetid: 09f458ac-dd88-4cd7-a47f-4106c1e80ece
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 5114f6015d055c03d54d49deee1197b7e3d9c9da
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62779466"
---
# <a name="ca1012-abstract-types-should-not-have-constructors"></a>CA1012:抽象型にはコンストラクターを含めません

|||
|-|-|
|TypeName|AbstractTypesShouldNotHaveConstructors|
|CheckId|CA1012|
|Category|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

型は abstract であり、コンス トラクターがあります。

既定では、このルールのみが検索に、外部から参照の種類が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

抽象型上のコンストラクターは、派生型からのみ呼び出すことができます。 パブリック コンス トラクターが型のインスタンスを作成し、抽象型のインスタンスを作成することはできません、ため、パブリック コンス トラクターを持つ抽象型のデザインは不適切です。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するのには、コンス トラクターを保護するか、または抽象型を宣言しないでください。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告は抑制しないでください。 抽象型では、パブリック コンス トラクターがあります。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1012.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (デザイン) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="example"></a>例

次のコード スニペットには、この規則に違反する抽象型が含まれています。

[!code-vb[FxCop.Design.AbstractTypeBad#1](../code-quality/codesnippet/VisualBasic/ca1012-abstract-types-should-not-have-constructors_1.vb)]
[!code-csharp[FxCop.Design.AbstractTypeBad#1](../code-quality/codesnippet/CSharp/ca1012-abstract-types-should-not-have-constructors_1.cs)]

次のコード スニペットからコンス トラクターのアクセシビリティを変更することで、前の違反を修正する`public`に`protected`します。

[!code-csharp[FxCop.Design.AbstractTypeGood#1](../code-quality/codesnippet/CSharp/ca1012-abstract-types-should-not-have-constructors_2.cs)]
[!code-vb[FxCop.Design.AbstractTypeGood#1](../code-quality/codesnippet/VisualBasic/ca1012-abstract-types-should-not-have-constructors_2.vb)]