---
title: 'CA1802: 適切な場所にリテラルを使用します。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseLiteralsWhereAppropriate
- CA1802
helpviewer_keywords:
- UseLiteralsWhereAppropriate
- CA1802
ms.assetid: 2515e4cd-9e61-486d-b067-58ba1a743ce4
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: bbcf83772a7a4031cf2e27abe7e8f4c08e21c11c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671512"
---
# <a name="ca1802-use-literals-where-appropriate"></a>CA1802: 適切な場所にリテラルを使用します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseLiteralsWhereAppropriate|
|CheckId|CA1802|
|カテゴリ|Microsoft. パフォーマンス|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 フィールドは `static` と `readonly` (`Shared` と `ReadOnly` [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) で宣言され、コンパイル時に計算できるという値を使用して初期化されます。

## <a name="rule-description"></a>規則の説明
 @No__t_0 フィールドの値は、宣言する型の静的コンストラクターが呼び出されるときに実行時に計算されます。 @No__t_0 フィールドが宣言時に初期化され、静的コンストラクターが明示的に宣言されていない場合、コンパイラはフィールドを初期化する静的コンストラクターを出力します。

 @No__t_0 フィールドの値はコンパイル時に計算され、メタデータに格納されます。これにより、`static``readonly` のフィールドと比較すると、実行時のパフォーマンスが向上します。

 コンパイル時には対象のフィールドに割り当てられた値が計算できるであるため、宣言を `const` フィールドに変更して、実行時ではなくコンパイル時に値が計算されるようにします。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、`static` および `readonly` 修飾子を `const` 修飾子で置き換えます。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 このルールからの警告を抑制することも、パフォーマンスが問題にならない場合はルールを無効にすることも安全です。

## <a name="example"></a>例
 次の例では、規則に違反する型 `UseReadOnly` が、規則に適合する型 `UseConstant` を示しています。

 [!code-csharp[FxCop.Performance.UseLiterals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.UseLiterals/cs/FxCop.Performance.UseLiterals.cs#1)]
 [!code-vb[FxCop.Performance.UseLiterals#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.UseLiterals/vb/FxCop.Performance.UseLiterals.vb#1)]
