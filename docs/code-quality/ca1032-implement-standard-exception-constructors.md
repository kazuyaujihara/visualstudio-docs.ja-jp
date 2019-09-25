---
title: CA1032:標準例外コンストラクターを実装します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1032
- ImplementStandardExceptionConstructors
helpviewer_keywords:
- CA1032
- ImplementStandardExceptionConstructors
ms.assetid: a8623c56-273a-4c95-8d83-95911a042be7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 06fdc566abd9bd16758f224f8a9fe805cddb2c61
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236045"
---
# <a name="ca1032-implement-standard-exception-constructors"></a>CA1032:標準例外コンストラクターを実装します

|||
|-|-|
|TypeName|ImplementStandardExceptionConstructors|
|CheckId|CA1032|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

型はを<xref:System.Exception?displayProperty=fullName>拡張しますが、すべての必要なコンストラクターを宣言するわけではありません。

## <a name="rule-description"></a>規則の説明

例外の種類では、次の3つのコンストラクターを実装する必要があります。

- public NewException ()

- public NewException (文字列)

- public NewException (文字列、例外)

さらに、 [.NET Compiler Platform ベースの fxcop アナライザー](../code-quality/roslyn-analyzers-overview.md)ではなく、従来の fxcop 分析を実行している場合、4番目のコンストラクターがないと、違反が発生します。

- protected または private NewException (SerializationInfo、StreamingContext)

コンストラクターを完全に宣言していないと、例外を正しく処理するのが困難になります。 たとえば、シグネチャ`NewException(string, Exception)`を持つコンストラクターは、他の例外によって発生する例外を作成するために使用されます。 このコンストラクターがないと、内部 (入れ子になった) 例外を含むカスタム例外のインスタンスを作成してスローすることはできません。このような状況では、マネージコードで実行する必要があります。

最初の3つの例外コンストラクターは規約によって公開されています。 4番目のコンストラクターは、封印されていないクラスで保護され、シールクラスでプライベートになります。 詳細については[、「CA2229:シリアル化コンストラクター](../code-quality/ca2229-implement-serialization-constructors.md)を実装します。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、不足しているコンストラクターを例外に追加し、適切なアクセシビリティが設定されていることを確認します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

パブリックコンストラクターに別のアクセスレベルを使用することによって違反が発生した場合に、この規則からの警告を抑制するのは安全です。 また、ポータブルクラスライブラリ (PCL) を構築し`NewException(SerializationInfo, StreamingContext)`ている場合は、コンストラクターの警告を抑制することもできます。

## <a name="example"></a>例

次の例には、この規則に違反する例外の種類と、正しく実装されている例外の種類が含まれています。

[!code-csharp[FxCop.Design.ExceptionMultipleCtors#1](../code-quality/codesnippet/CSharp/ca1032-implement-standard-exception-constructors_1.cs)]

## <a name="see-also"></a>関連項目

[CA2229: シリアル化コンストラクターを実装します](../code-quality/ca2229-implement-serialization-constructors.md)