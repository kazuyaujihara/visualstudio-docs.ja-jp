---
title: CA1504:紛らわしいフィールド名を確認します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ReviewMisleadingFieldNames
- CA1504
helpviewer_keywords:
- CA1504
- ReviewMisleadingFieldNames
ms.assetid: 94136ff1-4aaf-4dc2-9170-48c171ab7499
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 31c147c67854dd59f1fb7c9202f553edfb4a77a8
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234502"
---
# <a name="ca1504-review-misleading-field-names"></a>CA1504:紛らわしいフィールド名を確認します

|||
|-|-|
|TypeName|ReviewMisleadingFieldNames|
|CheckId|CA1504|
|カテゴリ|Microsoft の保守容易性|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
インスタンスフィールドの名前が "s_" で始まるか、または`static` (`Shared`内[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) フィールドの名前が "m_" で始まる。

## <a name="rule-description"></a>規則の説明
"S_" で始まるフィールド名は、多くのユーザーによって静的データに関連付けられています。 同様に、"m_" で始まるフィールド名は、インスタンス (メンバー) データに関連付けられています。 コードを保守しやすくするために、一般的に使用される規則に従う必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、適切なプレフィックスを使用してフィールドの名前を変更します。 または、 `static`修飾子を追加または削除して、フィールドが現在のサフィックスに一致するようにします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。