---
title: CA2214:コンストラクターのオーバーライド可能なメソッドを呼び出しません
ms.date: 05/29/2016
ms.topic: reference
f1_keywords:
- DoNotCallOverridableMethodsInConstructors
- CA2214
helpviewer_keywords:
- CA2214
- DoNotCallOverridableMethodsInConstructors
ms.assetid: 335b57ca-a6e8-41b4-a20e-57ee172c97c3
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a59346cb70269d4d2b405279fc9ea5573a879b1e
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547003"
---
# <a name="ca2214-do-not-call-overridable-methods-in-constructors"></a>CA2214:コンストラクターのオーバーライド可能なメソッドを呼び出しません

|||
|-|-|
|TypeName|DoNotCallOverridableMethodsInConstructors|
|CheckId|CA2214|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

シールされていない型のコンストラクターは、そのクラスで定義されている仮想メソッドを呼び出します。

## <a name="rule-description"></a>規則の説明

仮想メソッドが呼び出されると、メソッドを実行する実際の型は、実行時まで選択されません。 コンストラクターが仮想メソッドを呼び出す場合、メソッドを呼び出すインスタンスのコンストラクターが実行されていない可能性があります。

> [!NOTE]
> この規則のレガシ分析実装には、クラスによって定義**された仮想メソッドの呼び出しを結果とする呼び出しチェーンが含まれている "コンストラクター名"\[の異なる診断メッセージがあります。意図しない結果**を得るために、次の呼び出し履歴を確認します。 この規則の[FxCop アナライザー](install-fxcop-analyzers.md)の実装には、"**コンストラクターでオーバーライド可能なメソッドを呼び出さない**" という診断メッセージがあります。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、型のコンストラクター内から型の仮想メソッドを呼び出さないでください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。 仮想メソッドの呼び出しを避けるために、コンストラクターを再設計する必要があります。

## <a name="example"></a>例

次の例は、このルールに違反した場合の影響を示しています。 テストアプリケーションは、の`DerivedType`インスタンスを作成します。これにより、基本クラス (`BadlyConstructedType`) コンストラクターが実行されます。 `BadlyConstructedType`コンストラクターが仮想メソッド`DoSomething`を正しく呼び出すことができません。 出力が示すように`DerivedType.DoSomething()` 、は`DerivedType`、のコンストラクターが実行される前に実行されます。

[!code-csharp[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/CSharp/ca2214-do-not-call-overridable-methods-in-constructors_1.cs)]
[!code-vb[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/VisualBasic/ca2214-do-not-call-overridable-methods-in-constructors_1.vb)]

この例を実行すると、次の出力が生成されます。

```txt
Calling base ctor.
Derived DoSomething is called - initialized ? No
Calling derived ctor.
```