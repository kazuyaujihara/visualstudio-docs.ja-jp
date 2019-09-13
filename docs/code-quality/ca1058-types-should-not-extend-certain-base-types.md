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
ms.openlocfilehash: 38d92194a5aa2b46a0cb65a1525bc01d9de67b86
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547359"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058:型は、一定の基本型を拡張することはできません

|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

型は、次の基本型の1つを拡張します。

- <xref:System.ApplicationException?displayProperty=fullName>
- <xref:System.Xml.XmlDocument?displayProperty=fullName>
- <xref:System.Collections.CollectionBase?displayProperty=fullName>
- <xref:System.Collections.DictionaryBase?displayProperty=fullName>
- <xref:System.Collections.Queue?displayProperty=fullName>
- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>
- <xref:System.Collections.SortedList?displayProperty=fullName>
- <xref:System.Collections.Stack?displayProperty=fullName>

既定では、この規則は外部から参照できる型のみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

例外は、 <xref:System>名前<xref:System.Exception?displayProperty=fullName>空間のまたはそのサブクラスのいずれかから派生する必要があります。

基になるオブジェクトモデルまた<xref:System.Xml.XmlDocument>はデータソースの XML ビューを作成する場合は、のサブクラスを作成しないでください。

### <a name="non-generic-collections"></a>非ジェネリックコレクション

可能な限り、ジェネリックコレクションを使用するか、拡張します。 以前に配布していない限り、コード内の非ジェネリックコレクションは拡張しないでください。

**不適切な使用例**

```csharp
public class MyCollection : CollectionBase
{
}

public class MyReadOnlyCollection : ReadOnlyCollectionBase
{
}
```

**正しい使用例**

```csharp
public class MyCollection : Collection<T>
{
}

public class MyReadOnlyCollection : ReadOnlyCollection<T>
{
}
```

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、別の基本データ型またはジェネリックコレクションから型を派生させます。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

の違反について<xref:System.ApplicationException>は、この規則による警告を抑制しないでください。 の違反<xref:System.Xml.XmlDocument>については、この規則による警告を抑制することが安全です。 以前にコードがリリースされた場合、非ジェネリックコレクションに関する警告を抑制するのは安全です。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca1058.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (デザイン) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。