---
title: CA1058:型は、一定の基本型を拡張することはできません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5d88f08746035792913601b280a0794a9ff50bf2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62795763"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058:型は、一定の基本型を拡張することはできません

|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

型は、次の基本型の 1 つを拡張します。

- <xref:System.ApplicationException?displayProperty=fullName>
- <xref:System.Xml.XmlDocument?displayProperty=fullName>
- <xref:System.Collections.CollectionBase?displayProperty=fullName>
- <xref:System.Collections.DictionaryBase?displayProperty=fullName>
- <xref:System.Collections.Queue?displayProperty=fullName>
- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>
- <xref:System.Collections.SortedList?displayProperty=fullName>
- <xref:System.Collections.Stack?displayProperty=fullName>

既定では、このルールのみが検索に、外部から参照の種類が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

新しい例外を派生する .NET framework バージョン 1 では、推奨された<xref:System.ApplicationException>します。 推奨設定が変更され、新しい例外の派生元<xref:System.Exception?displayProperty=fullName>またはそのサブクラス内の 1 つ、<xref:System>名前空間。

サブクラスを作成しない<xref:System.Xml.XmlDocument>かどうかは、基になるオブジェクト モデルまたはデータ ソースの XML ビューを作成します。

### <a name="non-generic-collections"></a>非ジェネリック コレクション

使用して、または可能であれば、ジェネリック コレクションを拡張します。 以前に発送した場合を除き、コードで、非ジェネリック コレクションは拡張されません。

**不適切な使用方法の例**

```csharp
public class MyCollection : CollectionBase
{
}

public class MyReadOnlyCollection : ReadOnlyCollectionBase
{
}
```

**正しい使用法の例**

```csharp
public class MyCollection : Collection<T>
{
}

public class MyReadOnlyCollection : ReadOnlyCollection<T>
{
}
```

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するのには、別の基本型またはジェネリック コレクションから型を派生します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

詳細についてはこの規則違反の警告を抑制しないでください<xref:System.ApplicationException>します。 この規則違反の警告を抑制するには、安全では<xref:System.Xml.XmlDocument>します。 コードが以前にリリースされた場合は、非ジェネリック コレクションについて警告を抑制しても安全です。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1058.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (デザイン) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。