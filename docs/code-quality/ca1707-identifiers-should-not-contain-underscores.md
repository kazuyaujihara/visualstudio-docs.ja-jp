---
title: CA1707:識別子はアンダースコアを含むことはできません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotContainUnderscores
- CA1707
helpviewer_keywords:
- CA1707
- IdentifiersShouldNotContainUnderscores
ms.assetid: 5fb539ef-c304-4323-90c0-b14386da9774
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: adfa0ccd63d0433d367b0e7278693608bb83d685
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234267"
---
# <a name="ca1707-identifiers-should-not-contain-underscores"></a>CA1707:識別子はアンダースコアを含むことはできません

|||
|-|-|
|TypeName|IdentifiersShouldNotContainUnderscores|
|CheckId|CA1707|
|カテゴリ|Microsoft.Naming|
|互換性に影響する変更点|中断 (アセンブリで発生した場合)<br /><br /> 非中断 (型パラメーターで発生した場合)|

## <a name="cause"></a>原因

識別子の名前にアンダースコア (\_) 文字が含まれています。

## <a name="rule-description"></a>規則の説明

規則により、識別子名にはアンダースコア (\_) 文字は含まれません。 このルールは、名前空間、型、メンバー、およびパラメーターを確認します。

名前付け規則では、共通言語ランタイムをターゲットとするライブラリの統一的な名前の付け方が規定されています。 これにより、新しいソフトウェア ライブラリを習得するまでの時間を短縮でき、マネージド コード開発の専門家によってライブラリが開発されたという信頼を顧客に与えることができます。

## <a name="how-to-fix-violations"></a>違反の修正方法

名前からすべてのアンダースコア文字を削除します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。

## <a name="related-rules"></a>関連するルール

- [CA1709識別子は正しく使用する必要があります](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708識別子の大文字と小文字の区別が異なる場合](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
