---
title: CA2202:オブジェクトを複数回破棄しない
ms.date: 07/16/2019
ms.topic: reference
f1_keywords:
- CA2202
- Do not dispose objects multiple times
- DoNotDisposeObjectsMultipleTimes
helpviewer_keywords:
- CA2202
ms.assetid: fa85349a-cf1e-42c8-a86b-eacae1f8bd96
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7c7fa7756383426f990e18225995a768de9fefbd
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231737"
---
# <a name="ca2202-do-not-dispose-objects-multiple-times"></a>CA2202:オブジェクトを複数回破棄しない

|||
|-|-|
|TypeName|DoNotDisposeObjectsMultipleTimes|
|CheckId|CA2202|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

メソッドの実装に<xref:System.IDisposable.Dispose%2A?displayProperty=fullName>は、同じオブジェクトに対して、または一部の型の Close () メソッドなどの Dispose と同等のの呼び出しを発生させる可能性があるコードパスが含まれています。

## <a name="rule-description"></a>規則の説明

正しく実装<xref:System.IDisposable.Dispose%2A>されたメソッドは、例外をスローせずに複数回呼び出すことができます。 ただし、これは保証されていないため<xref:System.ObjectDisposedException?displayProperty=fullName> 、を生成し<xref:System.IDisposable.Dispose%2A>ないようにするには、オブジェクトでを複数回呼び出す必要があります。

## <a name="related-rules"></a>関連するルール

- [CA2000スコープを失う前にオブジェクトを破棄する](../code-quality/ca2000-dispose-objects-before-losing-scope.md)

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、コードパス<xref:System.IDisposable.Dispose%2A>に関係なく、オブジェクトに対して1回だけ呼び出されるように実装を変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。 オブジェクトが<xref:System.IDisposable.Dispose%2A>安全に複数回呼び出し可能であることがわかっている場合でも、実装は将来変更される可能性があります。

## <a name="example"></a>例

入れ子`using`になっ`Using`たステートメント (Visual Basic) では、CA2202 警告の違反が発生する可能性があります。 入れ子になった内側`using`のステートメントの IDisposable リソースに外側`using`のステートメントのリソースが含ま`Dispose`れている場合、入れ子になったリソースのメソッドは、含まれているリソースを解放します。 このような状況が発生`Dispose`すると、外側`using`のステートメントのメソッドは、そのリソースをもう一度破棄しようとします。

次の例では、 <xref:System.IO.Stream>外部の using ステートメントで作成されたオブジェクトが、 `stream`オブジェクトを含む<xref:System.IO.StreamWriter>オブジェクトの Dispose メソッド内の inner using ステートメントの最後に解放されます。 外側`using`のステートメント`stream`の最後では、オブジェクトが2回解放されます。 2番目のリリースは、CA2202 の違反です。

```csharp
using (Stream stream = new FileStream("file.txt", FileMode.OpenOrCreate))
{
    using (StreamWriter writer = new StreamWriter(stream))
    {
        // Use the writer object...
    }
}
```

## <a name="example"></a>例

この問題を解決するには`try` 、外側`using`のステートメントの代わりにブロックを/ `finally`使用します。 ブロックで、 `stream`リソースが null でないことを確認します。 `finally`

```csharp
Stream stream = null;
try
{
    stream = new FileStream("file.txt", FileMode.OpenOrCreate);
    using (StreamWriter writer = new StreamWriter(stream))
    {
        stream = null;
        // Use the writer object...
    }
}
finally
{
    stream?.Dispose();
}
```

> [!TIP]
> 上記の構文は、 [null 条件演算子です。](/dotnet/csharp/language-reference/operators/member-access-operators#null-conditional-operators--and-) `?.`

## <a name="see-also"></a>関連項目

- <xref:System.IDisposable?displayProperty=fullName>
- [Dispose パターン](/dotnet/standard/design-guidelines/dispose-pattern)