---
title: CA1041:ObsoleteAttribute メッセージを指定します
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: ad693014a7f6c16484f03c2d2f746c8159cf160e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62778868"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041:ObsoleteAttribute メッセージを指定します

|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|Category|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

使用して、型またはメンバーになって、<xref:System.ObsoleteAttribute?displayProperty=fullName>属性がないその<xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName>プロパティを指定します。

既定では、このルールだけが検索で外部から参照できる型とメンバーが、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

<xref:System.ObsoleteAttribute> 非推奨のライブラリの型およびメンバーを示すために使用します。 ライブラリのコンシューマーは、任意の型または不使用とマークされているメンバーの使用を避ける必要があります。 これは、サポートされない可能性がありますには最終的に、ライブラリの以降のバージョンから削除するためです。 型またはメンバーをマークを使用して<xref:System.ObsoleteAttribute>がコンパイルされる、<xref:System.ObsoleteAttribute.Message%2A>属性のプロパティが表示されます。 これによって、ユーザーは旧式の型またはメンバーに関する情報を知ることができます。 この情報には、旧式の型がどのくらいの時間通常が含まれます。 またはメンバーを使用するには、ライブラリの設計者と優先の交換によってサポートされます。

## <a name="how-to-fix-violations"></a>違反の修正方法

このルールの違反を修正するには、追加、`message`パラメーターを<xref:System.ObsoleteAttribute>コンス トラクター。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告を抑制しないでください、<xref:System.ObsoleteAttribute.Message%2A>プロパティは、旧式の型またはメンバーに関する重要な情報を提供します。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1041.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (デザイン) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="example"></a>例

次の例は、旧式のメンバーを持つ、正しく宣言<xref:System.ObsoleteAttribute>します。

[!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CPP/ca1041-provide-obsoleteattribute-message_1.cpp)]
[!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CSharp/ca1041-provide-obsoleteattribute-message_1.cs)]
[!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/VisualBasic/ca1041-provide-obsoleteattribute-message_1.vb)]

## <a name="see-also"></a>関連項目

- <xref:System.ObsoleteAttribute?displayProperty=fullName>