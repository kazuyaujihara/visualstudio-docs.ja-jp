---
title: 'CA2202: オブジェクトを複数回破棄することはできません |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2202
- Do not dispose objects multiple times
- DoNotDisposeObjectsMultipleTimes
helpviewer_keywords:
- CA2202
ms.assetid: fa85349a-cf1e-42c8-a86b-eacae1f8bd96
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: e0be715d8aea84fac53ea2a796e71850b961730c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72667397"
---
# <a name="ca2202-do-not-dispose-objects-multiple-times"></a>CA2202: オブジェクトを複数回破棄しません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotDisposeObjectsMultipleTimes|
|CheckId|CA2202|
|カテゴリ|Microsoft. 使用方法|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 メソッドの実装には、同じオブジェクトに対して、複数の呼び出し <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>、または一部の型の Close () メソッドなどの Dispose と同等の呼び出しが発生する可能性があるコードパスが含まれています。

## <a name="rule-description"></a>規則の説明
 正しく実装された <xref:System.IDisposable.Dispose%2A> メソッドは、例外をスローせずに複数回呼び出すことができます。 ただし、これは保証されておらず、<xref:System.ObjectDisposedException?displayProperty=fullName> を生成しないようにするために、1つのオブジェクトで <xref:System.IDisposable.Dispose%2A> を複数回呼び出すことは避けてください。

## <a name="related-rules"></a>関連規則
 [CA2000: スコープが失われる前にオブジェクトを破棄します](../code-quality/ca2000-dispose-objects-before-losing-scope.md)

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、コードパスに関係なく、<xref:System.IDisposable.Dispose%2A> がオブジェクトに対して1回だけ呼び出されるように実装を変更します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。 オブジェクトの <xref:System.IDisposable.Dispose%2A> が安全に呼び出すことができることがわかっている場合でも、実装は将来変更される可能性があります。

## <a name="example"></a>例
 入れ子になった `using` ステートメント (Visual Basic の `Using`) では、CA2202 警告が違反する可能性があります。 入れ子になった inner `using` ステートメントの IDisposable リソースに、外側の `using` ステートメントのリソースが含まれている場合、入れ子になったリソースの `Dispose` メソッドによって、含まれているリソースが解放されます。 このような状況が発生すると、外側の `using` ステートメントの `Dispose` メソッドは、そのリソースをもう一度破棄しようとします。

 次の例では、外側の using ステートメントで作成された <xref:System.IO.Stream> オブジェクトが、`stream` オブジェクトを含む <xref:System.IO.StreamWriter> オブジェクトの Dispose メソッド内の内側の using ステートメントの最後に解放されます。 外側の `using` ステートメントの最後では、`stream` オブジェクトが2回目に解放されます。 2番目のリリースは、CA2202 の違反です。

```
using (Stream stream = new FileStream("file.txt", FileMode.OpenOrCreate))
{
    using (StreamWriter writer = new StreamWriter(stream))
    {
        // Use the writer object...
    }
}
```

## <a name="example"></a>例
 この問題を解決するには、外部 `using` ステートメントの代わりに `try` / `finally` ブロックを使用します。 @No__t_0 ブロックで、`stream` リソースが null でないことを確認します。

```
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
    if(stream != null)
        stream.Dispose();
}
```

## <a name="see-also"></a>参照
 <xref:System.IDisposable?displayProperty=fullName> [Dispose パターン](https://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)
