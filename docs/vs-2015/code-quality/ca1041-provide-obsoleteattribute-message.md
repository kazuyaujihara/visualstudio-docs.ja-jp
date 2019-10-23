---
title: 'CA1041: ObsoleteAttribute message | を指定します。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: dd1799f67036ab55de5b136d746ce938835de87f
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72668325"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041: ObsoleteAttribute メッセージを指定します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 型またはメンバーが、<xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName> プロパティが指定されていない <xref:System.ObsoleteAttribute?displayProperty=fullName> 属性を使用してマークされています。

## <a name="rule-description"></a>規則の説明
 <xref:System.ObsoleteAttribute> は、非推奨のライブラリの型とメンバーをマークするために使用されます。 ライブラリコンシューマーは、古い形式に設定されている型またはメンバーを使用しないようにする必要があります。 これは、サポートされていない可能性があり、最終的にはライブラリの新しいバージョンから削除されるためです。 @No__t_0 を使用してマークされている型またはメンバーがコンパイルされると、その属性の <xref:System.ObsoleteAttribute.Message%2A> プロパティが表示されます。 これによって、ユーザーは旧式の型またはメンバーに関する情報を知ることができます。 通常、この情報には、ライブラリデザイナーによって使用されていない型またはメンバーがサポートされる期間、および使用する代わりに使用する代替の長さが含まれます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、<xref:System.ObsoleteAttribute> コンストラクターに `message` パラメーターを追加します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 @No__t_0 プロパティは、互換性のために残されている型またはメンバーに関する重要な情報を提供するため、この規則による警告を抑制しないでください。

## <a name="example"></a>例
 次の例は、<xref:System.ObsoleteAttribute> が正しく宣言されている古いメンバーを示しています。

 [!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/cpp/FxCop.Design.ObsoleteAttributeOnMember.cpp#1)]
 [!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/cs/FxCop.Design.ObsoleteAttributeOnMember.cs#1)]
 [!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/vb/FxCop.Design.ObsoleteAttributeOnMember.vb#1)]

## <a name="see-also"></a>参照
 <xref:System.ObsoleteAttribute?displayProperty=fullName>
