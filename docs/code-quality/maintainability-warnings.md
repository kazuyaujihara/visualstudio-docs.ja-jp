---
title: 保守性に関する警告
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- warnings, maintainability
- managed code analysis warnings, maintainability warnings
- maintainability warnings
ms.assetid: 537e70ca-a88c-49df-bfc7-0ee63bbe4f16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 79e9e24e7769cf4c632faab7795fe2f67844fe7d
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72445683"
---
# <a name="maintainability-warnings"></a>保守性に関する警告

保守容易性の警告により、ライブラリとアプリケーションのメンテナンスがサポートされます。

## <a name="in-this-section"></a>このセクションの内容

| 規則 | 説明 |
|-----------|-----------------------------------|
| [CA1500: 変数名はフィールド名と同一にすることはできません](../code-quality/ca1500-variable-names-should-not-match-field-names.md) | インスタンスメソッドは、宣言する型のインスタンスフィールドと名前が一致するパラメーターまたはローカル変数を宣言します。これにより、エラーが発生します。 |
| [CA1501: 継承を使用しすぎないでください](../code-quality/ca1501-avoid-excessive-inheritance.md) | 型が、その継承階層内の 5 つ以上深いレベルにあります。 深いレベルで入れ子にされた型の確認、理解、および保守は困難です。 |
| [CA1502: メソッドの実装を複雑にしすぎないでください](../code-quality/ca1502-avoid-excessive-complexity.md) | この規則は、線形独立のメソッド経路数を示す尺度で、条件分岐の数と複雑さによって決まります。 |
| [CA1504: 紛らわしいフィールド名をレビューします](../code-quality/ca1504-review-misleading-field-names.md) | インスタンスフィールドの名前が "s_" で始まるか、または静的な (共有 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) フィールドの名前が "m_" で始まります。 |
| [CA1505: メンテナンスできないコードを使用しないでください](../code-quality/ca1505-avoid-unmaintainable-code.md) | 型またはメソッドの保守容易性指数が低い値です。 保守容易性指数の低い型またはメソッドは、保守が困難な可能性があるため、デザインの変更を検討することをお勧めします。 |
| [CA1506: クラス結合度を大きくしすぎないでください](../code-quality/ca1506-avoid-excessive-class-coupling.md) | この規則は、型またはメソッドに含まれる一意の型参照の数をカウントすることによって、クラス結合度を計測します。 |
| [CA1507: 文字列の代わりに文字列を使用します。](../code-quality/ca1507.md) | 文字列リテラルは、`nameof` 式を使用できる引数として使用されます。 |

## <a name="see-also"></a>関連項目

- [マネージコードの複雑さと保守性の測定](../code-quality/code-metrics-values.md)
