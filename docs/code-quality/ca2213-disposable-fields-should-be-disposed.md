---
title: CA2213:破棄可能なフィールドは破棄されなければなりません
ms.date: 05/14/2019
ms.topic: reference
f1_keywords:
- DisposableFieldsShouldBeDisposed
- CA2213
helpviewer_keywords:
- CA2213
- DisposableFieldsShouldBeDisposed
ms.assetid: e99442c9-70e2-47f3-b61a-d8ac003bc6e5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 675206bb58e27110af79c46b1d61e9489f7661f2
ms.sourcegitcommit: 0f44ec8ba0263056ad04d2d0dc904ad4206ce8fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70766081"
---
# <a name="ca2213-disposable-fields-should-be-disposed"></a>CA2213:破棄可能なフィールドは破棄されなければなりません

|||
|-|-|
|TypeName|DisposableFieldsShouldBeDisposed|
|CheckId|CA2213|
|Category|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

を実装する<xref:System.IDisposable?displayProperty=fullName>型は、も実装<xref:System.IDisposable>する型のフィールドを宣言します。 フィールドの<xref:System.IDisposable.Dispose%2A>メソッドが、宣言する型のメソッドによって呼び出されていません。 <xref:System.IDisposable.Dispose%2A>

## <a name="rule-description"></a>規則の説明

型は、そのすべてのアンマネージリソースを破棄します。 Rule CA2213 は、破棄可能な型 (つまり<xref:System.IDisposable>、を実装しているもの) `T`が、 `F`破棄可能な型`FT`のインスタンスであるフィールドを宣言しているかどうかを確認します。 格納して`F`いる型`T`のメソッドまたは初期化子内にローカルで作成されたオブジェクトが割り当てられている各フィールド`FT.Dispose`について、ルールはの呼び出しの検索を試みます。 この規則では、によっ`T.Dispose`て呼び出されたメソッドと1つ下のレベル (によっ`T.Dispose`て呼び出されたメソッドによって呼び出されたメソッド) を検索します。

> [!NOTE]
> [特別な場合](#special-cases)を除き、rule CA2213 は、格納されている型のメソッドおよび初期化子内でローカルに作成された破棄可能オブジェクトが割り当てられているフィールドに対してのみ発生します。 オブジェクトが型`T`の外で作成または割り当てられた場合、ルールは起動されません。 これにより、含まれている型がオブジェクトを破棄する責任を持たない場合に、ノイズが軽減されます。

### <a name="special-cases"></a>特殊なケース

また、割り当てられているオブジェクトがローカルに作成されていない場合でも、次の型のフィールドに対して Rule CA2213 を起動することもできます。

- <xref:System.IO.Stream?displayProperty=nameWithType>
- <xref:System.IO.TextReader?displayProperty=nameWithType>
- <xref:System.IO.TextWriter?displayProperty=nameWithType>
- <xref:System.Resources.IResourceReader?displayProperty=nameWithType>

これらの型のいずれかのオブジェクトをコンストラクターに渡し、それをフィールドに割り当てることは、新しく構築された型への*dispose の所有権の譲渡*を意味します。 つまり、新しく構築された型が、オブジェクトの破棄を担当するようになりました。 オブジェクトが破棄されていない場合は、CA2213 違反が発生します。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、 <xref:System.IDisposable.Dispose%2A>を実装<xref:System.IDisposable>する型のフィールドに対してを呼び出します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

次の場合は、この規則による警告を抑制しても安全です。

- フラグが設定された型は、フィールドに保持されているリソースを解放する責任を負いません (つまり、型には*dispose の所有権*がありません)。
- の呼び出し<xref:System.IDisposable.Dispose%2A>は、規則チェックよりも深い呼び出しレベルで発生します。

## <a name="example"></a>例

次のスニペットは、を`TypeA`実装<xref:System.IDisposable>する型を示しています。

[!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_1.cs)]

次のスニペットは、フィールド`TypeB`を破棄可能な型 (`TypeA`) `aFieldOfADisposableType`として宣言し、フィールドでを呼び<xref:System.IDisposable.Dispose%2A>出さないことによって、rule CA2213 に違反する型を示しています。

[!code-csharp[FxCop.Usage.IDisposableFields#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_2.cs)]

違反を修正するには`Dispose()` 、破棄可能なフィールドでを呼び出します。

```csharp
protected virtual void Dispose(bool disposing)
{
   if (!disposed)
   {
      // Dispose of resources held by this instance.
      aFieldOfADisposableType.Dispose();

      disposed = true;

      // Suppress finalization of this disposed instance.
      if (disposing)
      {
          GC.SuppressFinalize(this);
      }
   }
}
```

## <a name="see-also"></a>関連項目

- <xref:System.IDisposable?displayProperty=fullName>
- [Dispose パターン](/dotnet/standard/design-guidelines/dispose-pattern)