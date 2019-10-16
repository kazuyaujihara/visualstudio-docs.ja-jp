---
title: 'CA1001: 破棄可能なフィールドを所有する型は、破棄可能でなければなりません'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
helpviewer_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
ms.assetid: c85c126c-2b16-4505-940a-b5ddf873fb22
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e8f2f313dad5f412a1a4d983d785caad5e6022a8
ms.sourcegitcommit: 1507baf3a336bbb6511d4c3ce73653674831501b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72349446"
---
# <a name="ca1001-types-that-own-disposable-fields-should-be-disposable"></a>CA1001: 破棄可能なフィールドを所有する型は、破棄可能でなければなりません

|||
|-|-|
|TypeName|TypesThatOwnDisposableFieldsShouldBeDisposable|
|CheckId|CA1001|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|非互換性-型がアセンブリの外部で参照できない場合。<br /><br /> 中断-型がアセンブリの外部で参照可能な場合。|

## <a name="cause"></a>原因
クラスは、@no__t 0 の型のインスタンスフィールドを宣言して実装します。このクラスは、<xref:System.IDisposable> を実装していません。

## <a name="rule-description"></a>規則の説明
クラスは、所有しているアンマネージリソースを破棄するために <xref:System.IDisposable> インターフェイスを実装します。 @No__t 0 の型のインスタンスフィールドは、そのフィールドがアンマネージリソースを所有していることを示します。 @No__t-0 フィールドを宣言するクラスは、アンマネージリソースを間接的に所有しており、<xref:System.IDisposable> インターフェイスを実装する必要があります。 クラスがアンマネージリソースを直接所有していない場合は、ファイナライザーを実装しないでください。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには <xref:System.IDisposable> を実装し、<xref:System.IDisposable.Dispose%2A?displayProperty=fullName> メソッドから、フィールドの <xref:System.IDisposable.Dispose%2A> メソッドを呼び出します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、規則に違反するクラスと、<xref:System.IDisposable> を実装することによって規則を満たすクラスを示しています。 クラスがアンマネージリソースを直接所有していないため、クラスはファイナライザーを実装しません。

[!code-vb[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/VisualBasic/ca1001-types-that-own-disposable-fields-should-be-disposable_1.vb)]
[!code-csharp[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/CSharp/ca1001-types-that-own-disposable-fields-should-be-disposable_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA2213: 破棄可能なフィールドは破棄されなければなりません](../code-quality/ca2213.md)

[CA2216: 破棄できる型ではファイナライザーを宣言します](../code-quality/ca2216.md)

[CA2215: Dispose メソッドから基本クラスの破棄を呼び出します](../code-quality/ca2215.md)

[CA1049: ネイティブ リソースを所有する型は、破棄可能でなければなりません](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)