---
title: CA1721:プロパティ名は get メソッドと同一にすることはできません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
helpviewer_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
ms.assetid: 45a0e853-1f06-4688-af1b-cc634409e295
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e2b9c878f630d9e739efc46380ecdfc6555880be
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57869220"
---
# <a name="ca1721-property-names-should-not-match-get-methods"></a>CA1721:プロパティ名は get メソッドと同一にすることはできません

|||
|-|-|
|TypeName|PropertyNamesShouldNotMatchGetMethods|
|CheckId|CA1721|
|Category|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

メンバーの名前は、'Get' で始まるし、それ以外の場合、プロパティの名前に一致します。 たとえば、'GetColor' と '色' というプロパティがという名前のメソッドを含む型では、ルール違反が発生します。

既定では、このルールのみが検索で外部から参照できるメンバーとプロパティが、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

"Get" メソッドとプロパティには、それぞれの機能を明確に区別する名前を指定しなければなりません。

名前付け規則では、共通言語ランタイムをターゲットとするライブラリの統一的な名前の付け方が規定されています。 この一貫性では、新しいソフトウェア ライブラリに必要なライブラリがマネージ コード開発の専門知識を持っている人によって開発されたという信頼を顧客になり時間が短縮します。

## <a name="how-to-fix-violations"></a>違反の修正方法

名前を変更するは、'Get' が付いているメソッドの名前が一致しないようにします。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告は抑制しないでください。

> [!NOTE]
> IExtenderProvider インターフェイスを実装することで、"Get"メソッドが発生した場合は、この警告を除外することがあります。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1721.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (名前付け) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="example"></a>例

次の例には、メソッドとプロパティをこの規則に違反が含まれています。

[!code-csharp[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/CSharp/ca1721-property-names-should-not-match-get-methods_1.cs)]
[!code-vb[FxCop.Naming.GetMethod#1](../code-quality/codesnippet/VisualBasic/ca1721-property-names-should-not-match-get-methods_1.vb)]

## <a name="related-rules"></a>関連するルール

- [CA 1024:適切な場所のプロパティを使用します。](../code-quality/ca1024-use-properties-where-appropriate.md)