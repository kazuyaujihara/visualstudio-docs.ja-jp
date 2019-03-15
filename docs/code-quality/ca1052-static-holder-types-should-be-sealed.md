---
title: CA1052:スタティック ホルダー型はシールドされていなければなりません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldBeSealed
- CA1052
helpviewer_keywords:
- CA1052
- StaticHolderTypesShouldBeSealed
ms.assetid: 51a3165d-781e-4a55-aa0d-ea25fee7d4f2
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 46a8c9a4e22c7a54a4b2b68f95bb2b81f3a0888e
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57870387"
---
# <a name="ca1052-static-holder-types-should-be-sealed"></a>CA1052:スタティック ホルダー型はシールドされていなければなりません

|||
|-|-|
|TypeName|StaticHolderTypesShouldBeSealed|
|CheckId|CA1052|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

非抽象型が静的メンバーのみが含まれていますとで宣言されていない、[シール](/dotnet/csharp/language-reference/keywords/sealed)([NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)) 修飾子。

既定では、このルールのみが検索に、外部から参照の種類が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

Ca 1052 のルールでは、型が派生型でオーバーライド可能な機能を備えていないため、静的メンバーのみを含む型でを継承するように設計しないことを前提としています。 継承を意図していない型をマークする必要があります、`sealed`または`NotInheritable`基本データ型としての使用を禁止する修飾子。 このルールは、抽象クラスの場合は発生しません。

## <a name="how-to-fix-violations"></a>違反の修正方法

このルールの違反を修正するには、マークの種類は`sealed`または`NotInheritable`します。 .NET Framework 2.0 を対象としているまたは型としてマークする方は、後で、`static`または`Shared`します。 この方法では、クラスが作成されていることを防ぐために、プライベート コンス トラクターを宣言する必要はありません。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

型が継承するように設計する場合にのみ、このルールから警告を抑制します。 ない場合、`sealed`または`NotInheritable`修飾子が型が基本データ型として便利なことを示します。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1052.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (デザイン) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="example-of-a-violation"></a>違反の例

次の例では、規則に違反する型を示します。

[!code-csharp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_1.cs)]
[!code-vb[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/VisualBasic/ca1052-static-holder-types-should-be-sealed_1.vb)]
[!code-cpp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CPP/ca1052-static-holder-types-should-be-sealed_1.cpp)]

## <a name="fix-with-the-static-modifier"></a>Static 修飾子で修正します。

次の例を持つ型をマークすることでこの規則違反を修正する方法を示しています、`static`修飾子C#:

[!code-csharp[FxCop.Design.StaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_2.cs)]

## <a name="related-rules"></a>関連するルール

- [CA 1053:スタティック ホルダー型には、コンス トラクターはありません。](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)