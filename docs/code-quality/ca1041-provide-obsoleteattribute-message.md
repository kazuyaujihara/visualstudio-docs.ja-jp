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
ms.openlocfilehash: 6620ac646c7fe20de856185708effc9e1a331e57
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235852"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041:ObsoleteAttribute メッセージを指定します

|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

型またはメンバーが、 <xref:System.ObsoleteAttribute?displayProperty=fullName> <xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName>プロパティが指定されていない属性を使用してマークされています。

既定では、この規則は外部から参照できる型およびメンバーのみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

<xref:System.ObsoleteAttribute>は、非推奨のライブラリの型とメンバーをマークするために使用されます。 ライブラリコンシューマーは、古い形式に設定されている型またはメンバーを使用しないようにする必要があります。 これは、サポートされていない可能性があり、最終的にはライブラリの新しいバージョンから削除されるためです。 を使用<xref:System.ObsoleteAttribute>してマークされている型または<xref:System.ObsoleteAttribute.Message%2A>メンバーがコンパイルされると、属性のプロパティが表示されます。 これによって、ユーザーは旧式の型またはメンバーに関する情報を知ることができます。 通常、この情報には、ライブラリデザイナーによって使用されていない型またはメンバーがサポートされる期間、および使用する代わりに使用する代替の長さが含まれます。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、 `message` <xref:System.ObsoleteAttribute>コンストラクターにパラメーターを追加します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

プロパティは<xref:System.ObsoleteAttribute.Message%2A>互換性のために残されている型またはメンバーに関する重要な情報を提供するため、この規則による警告を抑制しないでください。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca1041.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (デザイン) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="example"></a>例

次の例は、が正しく宣言<xref:System.ObsoleteAttribute>されている古いメンバーを示しています。

[!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CPP/ca1041-provide-obsoleteattribute-message_1.cpp)]
[!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CSharp/ca1041-provide-obsoleteattribute-message_1.cs)]
[!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/VisualBasic/ca1041-provide-obsoleteattribute-message_1.vb)]

## <a name="see-also"></a>関連項目

- <xref:System.ObsoleteAttribute?displayProperty=fullName>