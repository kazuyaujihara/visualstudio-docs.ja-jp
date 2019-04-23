---
title: CA1506:クラス結合度を大きくしすぎないでください
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b655609548d3de293abe2adc0ec3fb5c6fcf297b
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59232484"
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506:クラス結合度を大きくしすぎないでください

|||
|-|-|
|TypeName|AvoidExcessiveClassCoupling|
|CheckId|CA1506|
|カテゴリ|Microsoft.Maintainability|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

型またはメソッドは、さまざまな種類と結び付いています。

## <a name="rule-description"></a>規則の説明

この規則は、型またはメソッドに含まれる一意の型参照の数をカウントすることによって、クラス結合度を計測します。

型およびメソッドを持つクラス結合度の高度な保守が困難なできます。 型と低い結合と高凝集度を示すメソッドを用意することをお勧めします。

## <a name="how-to-fix-violations"></a>違反の修正方法

この違反を修正するには結合されて型の数を減らすには、型またはメソッドを再設計してください。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

型またはメソッドが、大量の他の種類への依存関係があるにもかかわらず保守しやすいと見なさ場合に、この警告を除外します。

## <a name="see-also"></a>関連項目

- [保守性の警告](../code-quality/maintainability-warnings.md)
- [マネージド コードの複雑さと保守性の測定](../code-quality/code-metrics-values.md)