---
title: CA1014:アセンブリに CLSCompliantAttribute を設定します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
helpviewer_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
ms.assetid: 4fe57449-cf45-4745-bcd2-6345f1ed266d
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: f11a93380f149648ece4ae6d71bc9c2f25df5191
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923117"
---
# <a name="ca1014-mark-assemblies-with-clscompliantattribute"></a>CA1014:アセンブリに CLSCompliantAttribute を設定します

|||
|-|-|
|TypeName|MarkAssembliesWithClsCompliant|
|CheckId|CA1014|
|Category|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
アセンブリに<xref:System.CLSCompliantAttribute?displayProperty=fullName>属性が適用されていません。

## <a name="rule-description"></a>規則の説明
共通言語仕様 (CLS) には、名前付けの制約、データ型、および規則が定義されています。アセンブリを複数のプログラミング言語で使用する場合、この仕様に準拠する必要があります。 優れた設計では、すべてのアセンブリがの<xref:System.CLSCompliantAttribute>CLS 準拠を明示的に示します。 属性がアセンブリに存在しない場合、アセンブリは準拠していません。

CLS 準拠のアセンブリには、準拠していない型または型のメンバーが含まれている可能性があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、属性をアセンブリに追加します。 アセンブリ全体を非準拠としてマークするのではなく、準拠していない型または型のメンバーを判断し、これらの要素をそのようにマークする必要があります。 可能であれば、最も多くのユーザーがアセンブリのすべての機能にアクセスできるように、準拠していないメンバーに対して CLS 準拠の代替手段を提供する必要があります。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。 アセンブリが準拠しないようにするには、属性を適用し、その値を`false`に設定します。

## <a name="example"></a>例
次の例は、CLS 準拠である<xref:System.CLSCompliantAttribute?displayProperty=fullName>ことを宣言する属性が適用されているアセンブリを示しています。

[!code-csharp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CSharp/ca1014-mark-assemblies-with-clscompliantattribute_1.cs)]
[!code-cpp[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/CPP/ca1014-mark-assemblies-with-clscompliantattribute_1.cpp)]
[!code-vb[FxCop.Design.AssembliesCls#1](../code-quality/codesnippet/VisualBasic/ca1014-mark-assemblies-with-clscompliantattribute_1.vb)]

## <a name="see-also"></a>関連項目

- <xref:System.CLSCompliantAttribute?displayProperty=fullName>
- [言語への非依存性、および言語非依存コンポーネント](/dotnet/standard/language-independence-and-language-independent-components)