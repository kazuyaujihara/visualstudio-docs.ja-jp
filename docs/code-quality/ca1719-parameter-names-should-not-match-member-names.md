---
title: CA1719:パラメーター名はメンバー名と同一にすることはできません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ParameterNamesShouldNotMatchMemberNames
- CA1719
helpviewer_keywords:
- CA1719
- ParameterNamesShouldNotMatchMemberNames
ms.assetid: c6fea690-1659-4ee7-a1c5-125ad6754525
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9b3e34bec0e199e1eb0b49a88517e9551b9b13cd
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921630"
---
# <a name="ca1719-parameter-names-should-not-match-member-names"></a>CA1719:パラメーター名はメンバー名と同一にすることはできません

|||
|-|-|
|TypeName|ParameterNamesShouldNotMatchMemberNames|
|CheckId|CA1719|
|Category|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
外部から参照できるメンバーの名前は、大文字と小文字を区別しない比較で、パラメーターの1つの名前に一致します。

## <a name="rule-description"></a>規則の説明
パラメーターはパラメーターの意味、メンバーはメンバーの意味を伝える名前にします。 この 2 つの名前が一致するデザインは、まれにしか見られません。 パラメーターにメンバーと同じ名前を付けるとわかりづらくなり、ライブラリの操作が難しくなります。

## <a name="how-to-fix-violations"></a>違反の修正方法
メンバー名と一致しないパラメーター名を選択してください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
新しい開発では、このルールの警告を抑制する必要がある既知のシナリオはありません。 配布ライブラリの場合、このルールからの警告を抑制することが必要になる場合があります。

## <a name="related-rules"></a>関連するルール
[CA1709識別子は正しく使用する必要があります](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

[CA1708識別子の大文字と小文字の区別が異なる場合](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

[CA1707識別子にアンダースコアを含めることはできません](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)