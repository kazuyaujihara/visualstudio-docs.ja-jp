---
title: 'CA1058: 型は、特定の基本型を拡張することはできません |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
caps.latest.revision: 26
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 9a4663fe3bc09b27bad9eeec05e325f07a3de6f3
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72603068"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: 型は、一定の基本型を拡張することはできません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 外部から参照可能な型では、特定の基本型が拡張されます。 現在、このルールは、次の型から派生した型を報告します。

- <xref:System.ApplicationException?displayProperty=fullName>

- <xref:System.Xml.XmlDocument?displayProperty=fullName>

- <xref:System.Collections.CollectionBase?displayProperty=fullName>

- <xref:System.Collections.DictionaryBase?displayProperty=fullName>

- <xref:System.Collections.Queue?displayProperty=fullName>

- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>

- <xref:System.Collections.SortedList?displayProperty=fullName>

- <xref:System.Collections.Stack?displayProperty=fullName>

## <a name="rule-description"></a>規則の説明
 @No__t_0 バージョン1では、<xref:System.ApplicationException> から新しい例外を派生させることをお勧めします。 推奨事項が変更され、新しい例外は <xref:System.Exception?displayProperty=fullName> または <xref:System> 名前空間のサブクラスの1つから派生する必要があります。

 基になるオブジェクトモデルまたはデータソースの XML ビューを作成する場合は、<xref:System.Xml.XmlDocument> のサブクラスを作成しないでください。

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

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 @No__t_0 に関する違反については、このルールからの警告を抑制しないでください。 @No__t_0 に関する違反については、このルールからの警告を抑制しても安全です。 以前にコードがリリースされた場合、非ジェネリックコレクションに関する警告を抑制するのは安全です。
