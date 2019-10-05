---
title: CA1047:シールド型の保護されたメンバーを宣言しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotDeclareProtectedMembersInSealedTypes
- CA1047
helpviewer_keywords:
- CA1047
- DoNotDeclareProtectedMembersInSealedTypes
ms.assetid: 829033b5-a9d8-4f26-a719-45494c9dd035
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 3114ea004c425567ae479343e0449d2cbc3aa669
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235704"
---
# <a name="ca1047-do-not-declare-protected-members-in-sealed-types"></a>CA1047:シールド型の保護されたメンバーを宣言しません

|||
|-|-|
|TypeName|DoNotDeclareProtectedMembersInSealedTypes|
|CheckId|CA1047|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
パブリック型は ( `sealed` `NotInheritable` Visual basic では) であり、プロテクトメンバーまたは protected 入れ子にされた型を宣言します。 この規則は、メソッドの<xref:System.Object.Finalize%2A>違反を報告しません。このパターンに従う必要があります。

## <a name="rule-description"></a>規則の説明
型でプロテクト メンバーを宣言するのは、継承する型からメンバーにアクセスまたはオーバーライドできるようにするためです。 定義上、シール型から継承することはできません。つまり、シール型のプロテクトメソッドを呼び出すことはできません。

コンパイラC#は、このエラーの警告を発行します。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、メンバーのアクセスレベルをプライベートに変更するか、型を継承可能にします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。 型を現在の状態のままにすると、メンテナンスの問題が発生する可能性があるため、利点はありません。

## <a name="example"></a>例
次の例は、この規則に違反する型を示しています。

[!code-vb[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/VisualBasic/ca1047-do-not-declare-protected-members-in-sealed-types_1.vb)]
[!code-csharp[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/CSharp/ca1047-do-not-declare-protected-members-in-sealed-types_1.cs)]