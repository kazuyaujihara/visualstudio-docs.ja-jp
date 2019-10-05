---
title: CA1722:識別子は不適切なプレフィックスを含むことはできません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotHaveIncorrectPrefix
- CA1722
helpviewer_keywords:
- CA1722
- IdentifiersShouldNotHaveIncorrectPrefix
ms.assetid: c3313c51-d004-4f9a-a0d1-6c4c4a1fb1e6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: eb41f2ad4548933d10137e7f72cae59643d33043
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233876"
---
# <a name="ca1722-identifiers-should-not-have-incorrect-prefix"></a>CA1722:識別子は不適切なプレフィックスを含むことはできません

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectPrefix|
|CheckId|CA1722|
|カテゴリ|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
識別子のプレフィックスが正しくありません。

## <a name="rule-description"></a>規則の説明
規則では、特定のプログラミング要素にのみ、固有のプレフィックスで始まる名前を付けることができます。

型名には特定のプレフィックスがなく、先頭に ' C ' を付けることはできません。 このルールは、' CMyClass ' などの型名の違反を報告し、' Cache ' などの型名の違反を報告しません。

名前付け規則では、共通言語ランタイムをターゲットとするライブラリの統一的な名前の付け方が規定されています。 この一貫性により、新しいソフトウェアライブラリに必要な学習曲線が減少し、マネージコードの開発に関する専門知識を持つユーザーによってライブラリが開発されたという自信が高まります。

## <a name="how-to-fix-violations"></a>違反の修正方法
識別子からプレフィックスを削除します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="related-rules"></a>関連するルール
[CA1715識別子は正しいプレフィックスを持つ必要があります](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)