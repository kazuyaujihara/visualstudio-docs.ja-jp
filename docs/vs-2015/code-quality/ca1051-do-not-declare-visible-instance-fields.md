---
title: 'CA1051: 参照可能なインスタンスフィールドを宣言しません |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 41332ab7d729f7b2187ccace6b05fe2d17763a0d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672519"
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051: 参照できるインスタンス フィールドを宣言しないでください
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 外部から参照できる型には、外部から参照できるインスタンスフィールドがあります。

## <a name="rule-description"></a>規則の説明
 フィールドの主な用途は、実装の詳細にする必要があります。 フィールドは `private` または `internal` である必要があり、プロパティを使用して公開する必要があります。 フィールドにアクセスするのと同じように、プロパティにアクセスするのは簡単です。プロパティのアクセサーのコードは、互換性に影響する変更を導入しなくても、型の機能が拡張されると変化することがあります。 プライベートフィールドまたは内部フィールドの値を返すプロパティは、フィールドへのアクセスと同等に動作するように最適化されています。パフォーマンスの向上は、プロパティを介して外部から参照できるフィールドを使用することに関連しています。

 外部から参照できるのは、`public`、`protected`、および `protected internal` (`Public`、`Protected`、`Protected Friend`) アクセシビリティレベルです。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、フィールドを `private` または `internal` し、外部から参照できるプロパティを使用して公開します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。 外部から参照できるフィールドには、プロパティで使用できない利点はありません。 また、パブリックフィールドを[リンク確認要求](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)で保護することはできません。 「 [CA2112: セキュリティで保護された型はフィールドを公開しない」を](../code-quality/ca2112-secured-types-should-not-expose-fields.md)参照してください。

## <a name="example"></a>例
 次の例は、この規則に違反する型 (`BadPublicInstanceFields`) を示しています。 `GoodPublicInstanceFields`、修正されたコードが表示されます。

 [!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TypesPublicInstanceFields/cs/FxCop.Design.TypesPublicInstanceFields.cs#1)]

## <a name="related-rules"></a>関連規則
 [CA2112: セキュリティで保護された型はフィールドを公開してはなりません](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>参照
 [リンク確認要求](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)
