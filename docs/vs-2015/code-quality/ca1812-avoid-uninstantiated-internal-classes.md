---
title: 'CA1812: インスタンス内部クラスを回避します。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1812
- AvoidUninstantiatedInternalClasses
helpviewer_keywords:
- AvoidUninstantiatedInternalClasses
- CA1812
ms.assetid: 1bb92a42-322a-44cc-98a8-8858212c1e1f
caps.latest.revision: 28
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: f5a36ee8cffc221d15243ff72e2e71558e867319
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72645405"
---
# <a name="ca1812-avoid-uninstantiated-internal-classes"></a>CA1812: インスタンス化されていない内部クラスを使用しないでください
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidUninstantiatedInternalClasses|
|CheckId|CA1812|
|カテゴリ|Microsoft. パフォーマンス|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 アセンブリ レベルの型のインスタンスが、アセンブリ内のコードから作成されません。

## <a name="rule-description"></a>規則の説明
 このルールは、型のいずれかのコンストラクターへの呼び出しを検索し、呼び出しが見つからない場合は違反を報告します。

 この規則では、次の型は検証されません。

- 値型

- 抽象型

- 列挙

- デリゲート

- コンパイラによって生成された配列型

- インスタンス化できず、`static` (Visual Basic) メソッドの `Shared` を定義する型。

  分析されるアセンブリに <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute?displayProperty=fullName> を適用すると、そのフィールドが別の `friend` アセンブリによって使用されているかどうかを判断できないため、`internal` としてマークされているコンストラクターに対してこの規則は発生しません。

  @No__t_0 コード分析でこの制限を回避することはできませんが、すべての `friend` アセンブリが分析に存在する場合は、外部のスタンドアロン FxCop が内部コンストラクターで発生します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、型を削除するか、この規則を使用するコードを追加します。 型に静的メソッドのみが含まれている場合は、次のいずれかを型に追加して、コンパイラが既定のパブリックインスタンスコンストラクターを生成しないようにします。

- @No__t_0 バージョン1.0 および1.1 を対象とする型のプライベートコンストラクター。

- @No__t_2 を対象とする型の `static` (Visual Basic で `Shared`) 修飾子。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 このルールからの警告を抑制するのは安全です。 次の状況では、この警告を非表示にすることをお勧めします。

- クラスは、<xref:System.Activator.CreateInstance%2A?displayProperty=fullName> などの遅延バインディングされたリフレクションメソッドを使用して作成されます。

- クラスは、ランタイムまたは [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] によって自動的に作成されます。 たとえば、<xref:System.Configuration.IConfigurationSectionHandler?displayProperty=fullName> または <xref:System.Web.IHttpHandler?displayProperty=fullName> を実装するクラスなどです。

- クラスは、新しい制約を持つジェネリック型パラメーターとして渡されます。 たとえば、次の例では、このルールが発生します。

  ```csharp
  internal class MyClass
  {
      public DoSomething()
      {
      }
  }
  public class MyGeneric<T> where T : new()
  {
      public T Create()
      {
          return new T();
      }
  }
  // [...]
  MyGeneric<MyClass> mc = new MyGeneric<MyClass>();
  mc.Create();
  ```

  このような状況では、この警告を非表示にすることをお勧めします。

## <a name="related-rules"></a>関連規則
 [CA1811: 呼び出されていないプライベート コードを使用しません](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1801: 使用されていないパラメーターをレビューします](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804: 使用されていないローカルを削除します](../code-quality/ca1804-remove-unused-locals.md)
