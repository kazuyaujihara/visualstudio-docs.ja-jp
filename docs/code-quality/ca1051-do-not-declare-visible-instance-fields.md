---
title: CA1051:参照可能なインスタンス フィールドを宣言しません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c5dd8a4b2d0b32a8c52f75dee6fd765a7ea6ec9a
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547553"
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051:参照可能なインスタンス フィールドを宣言しません

|||
|-|-|
|TypeName|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

型には、プライベートでないインスタンスフィールドがあります。

既定では、この規則は外部から参照できる型のみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

フィールドの主な用途は、実装の詳細にする必要があります。 フィールドは`private`または`internal`である必要があります。また、プロパティを使用して公開する必要があります。 フィールドにアクセスするのと同じように、プロパティにアクセスするのは簡単です。プロパティのアクセサーのコードは、互換性に影響する変更を導入しなくても、型の機能が拡張されると変化することがあります。 プライベートフィールドまたは内部フィールドの値を返すプロパティは、フィールドへのアクセスと同等に動作するように最適化されています。パフォーマンスの向上は、プロパティを介して外部から参照できるフィールドを使用することに関連しています。

外部から参照できる`public`の`protected`は、 `protected internal` 、`Public`、および(`Protected`Visual Basic) アクセシビリティレベルのです。`Protected Friend`

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、フィールド`private`をまたは`internal`に設定し、外部から参照できるプロパティを使用して公開します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。 外部から参照できるフィールドには、プロパティで使用できない利点はありません。 また、パブリックフィールドを[リンク確認要求](/dotnet/framework/misc/link-demands)で保護することはできません。 CA2112 [を参照してください。セキュリティで保護された](../code-quality/ca2112-secured-types-should-not-expose-fields.md)型はフィールドを公開しません。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca1051.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (デザイン) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="example"></a>例

次の例は、この規則`BadPublicInstanceFields`に違反する型 () を示しています。 `GoodPublicInstanceFields`修正されたコードを表示します。

[!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]

## <a name="related-rules"></a>関連するルール

- [CA2112セキュリティで保護された型はフィールドを公開しません](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>関連項目

- [リンク確認要求](/dotnet/framework/misc/link-demands)