---
title: CA1053:スタティック ホルダー型はコンストラクターを含むことはできません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldNotHaveConstructors
- CA1053
helpviewer_keywords:
- CA1053
- StaticHolderTypesShouldNotHaveConstructors
ms.assetid: 10302b9a-fa5e-4935-a06a-513d9600f613
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 44bdb8c12b48a983b88e6a035fc1522856b306be
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235583"
---
# <a name="ca1053-static-holder-types-should-not-have-default-constructors"></a>CA1053:静的ホルダー型に既定のコンストラクターを含めることはできません

|||
|-|-|
|TypeName|StaticHolderTypesShouldNotHaveConstructors|
|CheckId|CA1053|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

> [!NOTE]
> Rule CA1053 は CA1052 に[結合されます。静的ホルダー型は、](ca1052-static-holder-types-should-be-sealed.md) [FxCop アナライザー](fxcop-analyzers.yml)に封印する必要があります。

## <a name="cause"></a>原因

パブリックまたは入れ子にされたパブリック型は静的メンバーのみを宣言し、既定のコンストラクターを持ちます。

## <a name="rule-description"></a>規則の説明

静的メンバーを呼び出す場合、型のインスタンスは必要ないため、既定のコンストラクターは不要です。 また、型には非静的メンバーがないため、インスタンスを作成しても、型のメンバーへのアクセスは提供されません。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、既定のコンストラクターを削除します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。 既定のコンストラクターが存在する場合は、型が静的な型でないことが示されます。