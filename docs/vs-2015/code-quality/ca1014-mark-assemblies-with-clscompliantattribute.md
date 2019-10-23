---
title: 'CA1014: CLSCompliantAttribute | を使用してアセンブリをマークします。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
helpviewer_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
ms.assetid: 4fe57449-cf45-4745-bcd2-6345f1ed266d
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 9408a7b55c800a7979c39075afdf8e9e6e4c7cdb
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663158"
---
# <a name="ca1014-mark-assemblies-with-clscompliantattribute"></a>CA1014: アセンブリに CLSCompliantAttribute を設定します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkAssembliesWithClsCompliant|
|CheckId|CA1014|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 アセンブリには、<xref:System.CLSCompliantAttribute?displayProperty=fullName> 属性が適用されていません。

## <a name="rule-description"></a>規則の説明
 共通言語仕様 (CLS) には、名前付けの制約、データ型、および規則が定義されています。アセンブリを複数のプログラミング言語で使用する場合、この仕様に準拠する必要があります。 優れた設計では、すべてのアセンブリが明示的に <xref:System.CLSCompliantAttribute> に CLS 準拠を示すことを示します。 属性がアセンブリに存在しない場合、アセンブリは準拠していません。

 CLS 準拠のアセンブリには、準拠していない型または型のメンバーが含まれている可能性があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、属性をアセンブリに追加します。 アセンブリ全体を非準拠としてマークするのではなく、準拠していない型または型のメンバーを判断し、これらの要素をそのようにマークする必要があります。 可能であれば、最も多くのユーザーがアセンブリのすべての機能にアクセスできるように、準拠していないメンバーに対して CLS 準拠の代替手段を提供する必要があります。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。 アセンブリが準拠しないようにするには、属性を適用し、その値を `false` に設定します。

## <a name="example"></a>例
 次の例は、CLS 準拠であることを宣言する <xref:System.CLSCompliantAttribute?displayProperty=fullName> 属性が適用されているアセンブリを示しています。

 [!code-cpp[FxCop.Design.AssembliesCls#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCls/cpp/FxCop.Design.AssembliesCls.cpp#1)]
 [!code-csharp[FxCop.Design.AssembliesCls#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCls/cs/FxCop.Design.AssembliesCls.cs#1)]
 [!code-vb[FxCop.Design.AssembliesCls#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCls/vb/FxCop.Design.AssembliesCls.vb#1)]

## <a name="see-also"></a>参照
 [言語への非依存性と言語に依存しないコンポーネントの](https://msdn.microsoft.com/library/4f0b77d0-4844-464f-af73-6e06bedeafc6)<xref:System.CLSCompliantAttribute?displayProperty=fullName>
