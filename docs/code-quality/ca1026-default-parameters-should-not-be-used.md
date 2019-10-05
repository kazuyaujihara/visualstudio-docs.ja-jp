---
title: CA1026:既定パラメーターを使用することはできません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
helpviewer_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
ms.assetid: 09643415-36ef-4d0f-9411-5721e14e2512
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 62de7654083f3fd64f95401f95e5ee593effb27d
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236132"
---
# <a name="ca1026-default-parameters-should-not-be-used"></a>CA1026:既定パラメーターを使用することはできません

|||
|-|-|
|TypeName|DefaultParametersShouldNotBeUsed|
|CheckId|CA1026|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
外部から参照できる型には、既定のパラメーターを使用する外部から参照できるメソッドが含まれています。

## <a name="rule-description"></a>規則の説明
既定のパラメーターを使用するメソッドは、共通言語仕様 (CLS) で許可されています。ただし、CLS では、これらのパラメーターに割り当てられている値をコンパイラで無視できます。 既定のパラメーター値を無視するコンパイラ用に記述されたコードでは、既定のパラメーターごとに引数を明示的に指定する必要があります。 プログラミング言語全体で必要な動作を維持するには、既定のパラメーターを使用するメソッドを、既定のパラメーターを指定するメソッドのオーバーロードに置き換える必要があります。

マネージコードにアクセスC++するときに、コンパイラはマネージ拡張の既定のパラメーターの値を無視します。 Visual Basic コンパイラは、[省略可能](/dotnet/visual-basic/language-reference/modifiers/optional)なキーワードを使用する既定のパラメーターを持つメソッドをサポートしています。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、既定のパラメーターを使用するメソッドを、既定のパラメーターを指定するメソッドのオーバーロードに置き換えます。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、既定のパラメーターを使用するメソッドと、同等の機能を提供するオーバーロードされたメソッドを示しています。

[!code-vb[FxCop.Design.DefaultParameters#1](../code-quality/codesnippet/VisualBasic/ca1026-default-parameters-should-not-be-used_1.vb)]

## <a name="related-rules"></a>関連するルール
[CA1025反復する引数を params 配列で置き換えます](../code-quality/ca1025-replace-repetitive-arguments-with-params-array.md)

## <a name="see-also"></a>関連項目
[言語への非依存性、および言語非依存コンポーネント](/dotnet/standard/language-independence-and-language-independent-components)