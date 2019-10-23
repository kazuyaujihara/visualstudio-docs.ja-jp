---
title: 'CA1717: FlagsAttribute 列挙型のみが複数形の名前を持つ必要があります |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1717
- OnlyFlagsEnumsShouldHavePluralNames
helpviewer_keywords:
- OnlyFlagsEnumsShouldHavePluralNames
- CA1717
ms.assetid: a6855d8b-d78a-42c1-834e-61c31f5572ed
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 0c378d419be0d964c27cfcbe523fbe3a33da97b8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72669083"
---
# <a name="ca1717-only-flagsattribute-enums-should-have-plural-names"></a>CA1717: FlagsAttribute 列挙のみが複数形の名前を含んでいなければなりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|OnlyFlagsEnumsShouldHavePluralNames|
|CheckId|CA1717|
|カテゴリ|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 外部から参照できる列挙型の名前が複数形で終了し、列挙が <xref:System.FlagsAttribute?displayProperty=fullName> 属性でマークされていません。

## <a name="rule-description"></a>規則の説明
 名前付け規則は、列挙体の複数形の名前が同時に指定できることを示します。 この <xref:System.FlagsAttribute> は、列挙体が列挙体に対してビットごとの演算を実行できるビットフィールドとして処理する必要があることをコンパイラに伝えます。

 列挙体の1つの値だけを一度に指定できる場合、列挙体の名前は単数形の単語である必要があります。 たとえば、曜日を定義する列挙体は、複数の日を指定できるアプリケーションで使用することが想定されています。 この列挙体には <xref:System.FlagsAttribute> が含まれている必要があり、"Days" という名前を付けることができます。 1つの日だけを指定できるようにする同様の列挙には、属性は含まれず、"Day" と呼ばれることもあります。

 名前付け規則では、共通言語ランタイムをターゲットとするライブラリの統一的な名前の付け方が規定されています。 これにより、新しいソフトウェアライブラリを学習するために必要な時間が短縮され、マネージコードの開発に関する専門知識を持つユーザーによってライブラリが開発されたという自信が高まります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 列挙型の名前を単数形の単語にするか、<xref:System.FlagsAttribute> を追加します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 名前が単数形で終わる場合は、ルールからの警告を抑制しても安全です。

## <a name="related-rules"></a>関連規則
 [CA1714: フラグ列挙は、複数形の名前を含んでいなければなりません](../code-quality/ca1714-flags-enums-should-have-plural-names.md)

 [CA1027: FlagsAttribute で列挙値をマークします](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: enums を FlagsAttribute に設定しません](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>参照
 <xref:System.FlagsAttribute?displayProperty=fullName>[列挙型のデザイン](https://msdn.microsoft.com/library/dd53c952-9d9a-4736-86ff-9540e815d545)
