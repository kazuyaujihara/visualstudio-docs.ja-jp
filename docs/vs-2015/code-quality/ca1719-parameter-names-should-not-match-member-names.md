---
title: CA1719:パラメーター名は、メンバー名と一致する必要があります |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ParameterNamesShouldNotMatchMemberNames
- CA1719
helpviewer_keywords:
- CA1719
- ParameterNamesShouldNotMatchMemberNames
ms.assetid: c6fea690-1659-4ee7-a1c5-125ad6754525
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: daaa856ccbc5915bcaad937a504ea2600a089c1d
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "58975427"
---
# <a name="ca1719-parameter-names-should-not-match-member-names"></a>CA1719:パラメーター名はメンバー名と同一にすることはできません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ParameterNamesShouldNotMatchMemberNames|
|CheckId|CA1719|
|カテゴリ|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 外部から参照できるメンバーの名前は、大文字と小文字をそのパラメーターの 1 つの名前と一致します。

## <a name="rule-description"></a>規則の説明
 パラメーターはパラメーターの意味、メンバーはメンバーの意味を伝える名前にします。 この 2 つの名前が一致するデザインは、まれにしか見られません。 パラメーターにメンバーと同じ名前を付けるとわかりづらくなり、ライブラリの操作が難しくなります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 メンバー名に一致しないパラメーター名を選択します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 新たに開発されていないシナリオが発生する、この規則による警告を抑制する必要があります。 ライブラリを配布するには、この規則による警告を抑制する必要があります。

## <a name="related-rules"></a>関連規則
 [CA 1709:識別子では、大文字と小文字が正しく区別する必要があります。](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

 [CA1708:識別子は、ケース以外で相違させる必要があります。](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

 [CA 1707:識別子はアンダー スコアを含めることはできません。](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)
