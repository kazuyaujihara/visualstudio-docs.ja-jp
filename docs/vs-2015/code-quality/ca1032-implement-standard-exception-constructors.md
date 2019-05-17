---
title: CA1032:標準例外コンストラクターの実装 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1032
- ImplementStandardExceptionConstructors
helpviewer_keywords:
- CA1032
- ImplementStandardExceptionConstructors
ms.assetid: a8623c56-273a-4c95-8d83-95911a042be7
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c59da56304a5d1d8f2cca7eaf886fd5ebc37f8ef
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973406"
---
# <a name="ca1032-implement-standard-exception-constructors"></a>CA1032:標準例外コンストラクターを実装します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ImplementStandardExceptionConstructors|
|CheckId|CA1032|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 型拡張<xref:System.Exception?displayProperty=fullName>し、必要なすべてのコンストラクターを宣言しません。

## <a name="rule-description"></a>規則の説明
 例外の種類には、次のコンストラクターを実装する必要があります。

- パブリック NewException()

- パブリック NewException(string)

- パブリック NewException (文字列、例外)

- 保護されたまたはプライベート NewException (SerializationInfo, StreamingContext)

  コンストラクターを完全に宣言していないと、例外を正しく処理するのが困難になります。 シグネチャを持つコンストラクターなど`NewException(string, Exception)`他の例外によって引き起こされる例外を作成するために使用します。 このコンストラクターのない作成して、インスタンスの内部の (入れ子になった) 例外を含む独自の例外をスローすることはできません、どのようなマネージ コードは、このような状況で行う必要がありますです。 最初の 3 つの例外のコンストラクターでは、規則でパブリックです。 4 番目のコンストラクターが封印されていないクラスで保護されているシール クラスではプライベートです。 詳細については、次を参照してください。 [ca 2229。シリアル化コンストラクターを実装します](../code-quality/ca2229-implement-serialization-constructors.md)

## <a name="how-to-fix-violations"></a>違反の修正方法
 このルールの違反を修正するには、例外に不足しているコンストラクターを追加し、適切なアクセシビリティであるかどうかを確認します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 パブリック コンストラクターを異なるアクセス レベルを使用して、違反が発生する場合、この規則による警告を抑制するのには安全です。

## <a name="example"></a>例
 次の例には、この規則に違反する例外の種類と例外の種類が正しく実装されているが含まれています。

 [!code-csharp[FxCop.Design.ExceptionMultipleCtors#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ExceptionMultipleCtors/cs/FxCop.Design.ExceptionMultipleCtors.cs#1)]
