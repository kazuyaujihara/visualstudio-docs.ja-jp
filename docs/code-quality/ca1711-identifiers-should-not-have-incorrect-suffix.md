---
title: CA1711:識別子は、不適切なサフィックスを含むことはできません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
helpviewer_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
ms.assetid: a63359ab-386d-44ae-b381-ee3a983aca29
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 83eff2b91a62d389f2273ff600e077eaea379d88
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57871890"
---
# <a name="ca1711-identifiers-should-not-have-incorrect-suffix"></a>CA1711:識別子は、不適切なサフィックスを含むことはできません

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectSuffix|
|CheckId|CA1711|
|Category|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

識別子のサフィックスが不適切です。

既定では、このルールだけを確認、外部から参照できる識別子が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

規則では、特定の基本型を拡張する型、特定のインターフェイスを実装する型、またはそのような型から派生した型の名前にのみ、固有の予約済みサフィックスを末尾に付けます。 その他の型名では、予約済みのサフィックスを使用しないでください。

予約済みのサフィックス、および関連付けられている基本型とインターフェイスを次の表に示します。

|サフィックス|基本型/インターフェイス|
|------------|--------------------------|
|属性|<xref:System.Attribute?displayProperty=fullName>|
|Collection|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|
|Dictionary|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|
|EventHandler|イベント ハンドラーのデリゲート|
|例外|<xref:System.Exception?displayProperty=fullName>|
|アクセス許可|<xref:System.Security.IPermission?displayProperty=fullName>|
|Queue|<xref:System.Collections.Queue?displayProperty=fullName>|
|Stack|<xref:System.Collections.Stack?displayProperty=fullName>|
|ストリーム|<xref:System.IO.Stream?displayProperty=fullName>|

さらに、次のサフィックスが必要があります**いない**使用します。

- `Delegate`

- `Enum`

- `Impl` (を使用して、`Core`代わりに)

- `Ex` または、同じ種類の以前のバージョンと区別するための類似のサフィックス

名前付け規則では、共通言語ランタイムをターゲットとするライブラリの統一的な名前の付け方が規定されています。 これにより、新しいソフトウェア ライブラリを習得するまでの時間を短縮でき、マネージド コード開発の専門家によってライブラリが開発されたという信頼を顧客に与えることができます。

## <a name="how-to-fix-violations"></a>違反の修正方法

型名からサフィックスを削除します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

アプリケーション ドメインでサフィックスに明確な意味がある場合を除き、この規則による警告を抑制しないでください。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1711.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (名前付け) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="related-rules"></a>関連するルール

- [CA1710:識別子は、正しいサフィックスをいなければなりません](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)

## <a name="see-also"></a>関連項目

- [属性](/dotnet/standard/design-guidelines/attributes)
- [処理とイベントの発生](/dotnet/standard/events/index)