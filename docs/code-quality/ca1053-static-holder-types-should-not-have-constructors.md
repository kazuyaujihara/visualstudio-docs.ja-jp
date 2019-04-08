---
title: CA1053:スタティック ホルダー型はコンストラクターを含むことはできません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldNotHaveConstructors
- CA1053
helpviewer_keywords:
- CA1053
- StaticHolderTypesShouldNotHaveConstructors
ms.assetid: 10302b9a-fa5e-4935-a06a-513d9600f613
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: da5edc8f31510fa01d2132735ede502ad7f6ad6a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55922603"
---
# <a name="ca1053-static-holder-types-should-not-have-constructors"></a>CA1053:スタティック ホルダー型はコンストラクターを含むことはできません

|||
|-|-|
|TypeName|StaticHolderTypesShouldNotHaveConstructors|
|CheckId|CA1053|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 パブリック型または入れ子になったパブリック型で、静的なメンバーのみが宣言されています。また、パブリックまたはプロテクトの既定のコンストラクターが含まれます。

## <a name="rule-description"></a>規則の説明
 静的メンバーの呼び出しに型のインスタンスは必要ないため、コンストラクターは不要です。 また、型が非静的メンバーを持たないためインスタンスを作成するアクセスことはできません型のメンバーのいずれかに。

## <a name="how-to-fix-violations"></a>違反の修正方法
 このルールの違反を修正するには、既定のコンス トラクターを削除するか、プライベートになります。

> [!NOTE]
>  型はコンス トラクターを定義していない場合、一部のコンパイラは自動的に既定のパブリック コンス トラクターを作成します。 型の場合は場合、違反を防ぐために既定のプライベート コンス トラクターを追加します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。
 この規則による警告は抑制しないでください。 コンス トラクターのプレゼンスは、型が静的な型ではないことを提案します。

## <a name="example"></a>例
 次の例では、この規則に違反する型を示します。 ソース コードで既定のコンス トラクターがないことに注意してください。 このコードがアセンブリにコンパイルされると、C# コンパイラは既定コンス トラクターは、このルールに違反するを挿入します。 これを修正するには、プライベート コンス トラクターを宣言します。

 [!code-csharp[FxCop.Design.StaticTypes#1](../code-quality/codesnippet/CSharp/ca1053-static-holder-types-should-not-have-constructors_1.cs)]