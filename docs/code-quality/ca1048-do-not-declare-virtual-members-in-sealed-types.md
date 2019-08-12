---
title: CA1048:シールド型の仮想メンバーを宣言しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
helpviewer_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
ms.assetid: 5dcf4a30-6f98-48a8-b8cc-7b89ea757262
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 430ed0b23d62bd46a9764bfb0a3834e0decd476b
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922594"
---
# <a name="ca1048-do-not-declare-virtual-members-in-sealed-types"></a>CA1048:シールド型の仮想メンバーを宣言しません

|||
|-|-|
|TypeName|DoNotDeclareVirtualMembersInSealedTypes|
|CheckId|CA1048|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
パブリック型はシールされており、( `virtual` `Overridable` Visual Basic の) 両方であり、final ではないメソッドを宣言します。 この規則は、このパターンに従う必要があるデリゲート型の違反を報告しません。

## <a name="rule-description"></a>規則の説明
型でメソッドを仮想と宣言するのは、継承する型が仮想メソッドの実装をオーバーライドできるようにするためです。 定義上、シール型から継承することはできません。シール型の仮想メソッドを使用することは無意味です。

Visual Basic とC#コンパイラでは、型がこの規則に違反することはありません。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、メソッドを非仮想にするか、型を継承可能にしてください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。 型を現在の状態のままにすると、メンテナンスの問題が発生する可能性があるため、利点はありません。

## <a name="example"></a>例
次の例は、この規則に違反する型を示しています。

[!code-cpp[FxCop.Design.SealedVirtual#1](../code-quality/codesnippet/CPP/ca1048-do-not-declare-virtual-members-in-sealed-types_1.cpp)]