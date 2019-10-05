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
ms.openlocfilehash: 1721fd52c00c5b312c88f19d48b668b12d28f050
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234491"
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506:クラス結合度を大きくしすぎないでください

|||
|-|-|
|TypeName|AvoidExcessiveClassCoupling|
|CheckId|CA1506|
|カテゴリ|Microsoft の保守容易性|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

型またはメソッドは、他の多くの型と結合されます。

## <a name="rule-description"></a>規則の説明

この規則は、型またはメソッドに含まれる一意の型参照の数をカウントすることによって、クラス結合度を計測します。

クラスの結合度が高い型およびメソッドは、保守が困難な場合があります。 結合率が低く、高い凝集度を示す型とメソッドを用意することをお勧めします。

## <a name="how-to-fix-violations"></a>違反の修正方法

この違反を修正するには、型またはメソッドを再設計して、結合される型の数を減らしてみてください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

型またはメソッドが、他の型に対する依存関係の数が多いにもかかわらず保守可能と見なされる場合は、この警告を除外します。

## <a name="see-also"></a>関連項目

- [保守性の警告](../code-quality/maintainability-warnings.md)
- [マネージド コードの複雑さと保守性の測定](../code-quality/code-metrics-values.md)