---
title: CA1800:不必要にキャストしない |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1800
- DoNotCastUnnecessarily
helpviewer_keywords:
- DoNotCastUnnecessarily
- CA1800
ms.assetid: b79a010a-6627-421e-8955-6007e32fa808
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 466309cef8905faa9b659e2d3652975d815767fb
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663105"
---
# <a name="ca1800-do-not-cast-unnecessarily"></a>CA1800:不必要にキャストしません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotCastUnnecessarily|
|CheckId|CA1800|
|カテゴリ|Microsoft. パフォーマンス|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 メソッドは、その引数の1つまたはローカル変数に対して重複するキャストを実行します。 この規則による完全な分析を行うには、デバッグ情報を使用してテストされたアセンブリをビルドし、関連付けられているプログラムデータベース (.pdb) ファイルを使用できるようにする必要があります。

## <a name="rule-description"></a>規則の説明
 二重のキャストがあるとパフォーマンスが低下します。特に、小さな繰り返しステートメントでキャストが実行される場合はそうです。 明示的な重複キャスト操作の場合は、キャストの結果をローカル変数に格納し、重複するキャスト操作の代わりにローカル変数を使用します。

 実際のC#キャストが実行される前にキャストが成功するかどうかをテストするために `is` 演算子が使用されている場合は、代わりに `as` 演算子の結果をテストすることを検討してください。 これにより、`is` 演算子によって実行される暗黙的なキャスト操作がなくても、同じ機能が提供されます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、メソッドの実装を変更して、キャスト操作の数を最小限にします。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 このルールからの警告を抑制することも、パフォーマンスが問題にならない場合は完全に無視することもできます。

## <a name="example"></a>例
 次の例は、 C# `is` 演算子を使用してルールに違反するメソッドを示しています。 2番目のメソッドは、`is` 演算子を `as` 演算子の結果に対してテストに置き換えることによって規則を満たします。これにより、反復ごとのキャスト操作の数が2から1に減少します。

 [!code-csharp[FxCop.Performance.UnnecessaryCastsAsIs#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.UnnecessaryCastsAsIs/cs/FxCop.Performance.UnnecessaryCastsAsIs.cs#1)]

## <a name="example"></a>例
 次の例は、複数の重複した明示的なキャスト (ルールに違反する) と、ローカル変数にキャストを格納することによってルールを満たすメソッド (`reset_Click`) を持つメソッド `start_Click` を示しています。

 [!code-csharp[FxCop.Performance.UnnecessaryCasts#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.UnnecessaryCasts/cs/FxCop.Performance.UnnecessaryCasts.cs#1)]
 [!code-vb[FxCop.Performance.UnnecessaryCasts#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.UnnecessaryCasts/vb/FxCop.Performance.UnnecessaryCasts.vb#1)]

## <a name="see-also"></a>関連項目
 [as](https://msdn.microsoft.com/library/a9be126b-cbf4-4990-a70d-d0e1983cad0e) [is](https://msdn.microsoft.com/library/bc62316a-d41f-4f90-8300-c6f4f0556e43)
