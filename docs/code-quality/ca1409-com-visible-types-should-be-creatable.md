---
title: CA1409:COM 参照可能な型は作成可能でなければなりません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
helpviewer_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
ms.assetid: 9f59569b-de15-4a38-b7cb-cff152972243
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 54630b7fba69ef96a2c08486e535ae45d8e614b8
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234765"
---
# <a name="ca1409-com-visible-types-should-be-creatable"></a>CA1409:COM 参照可能な型は作成可能でなければなりません

|||
|-|-|
|TypeName|ComVisibleTypesShouldBeCreatable|
|CheckId|CA1409|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
コンポーネントオブジェクトモデル (COM) に対して表示されるように明示的にマークされている参照型は、パブリックなパラメーター化されたコンストラクターを含んでいますが、パブリックな既定 (パラメーターなし) コンストラクターを含んでいません。

## <a name="rule-description"></a>規則の説明
パブリックな既定のコンストラクターを持たない型は、COM クライアントで作成できません。 ただし、型を作成し、それをクライアントに渡す (たとえば、メソッド呼び出しの戻り値を使用して) 場合、COM クライアントからもこの型にアクセスできます。

このルールは、から<xref:System.Delegate?displayProperty=fullName>派生した型を無視します。

既定では、アセンブリ、パブリック型、パブリック型のパブリックインスタンスメンバー、およびパブリック値型のすべてのメンバーに対して、COM から参照できます。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、パブリックの既定のコンストラクターを追加<xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName>するか、型からを削除します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
オブジェクトを作成して COM クライアントに渡すために他の方法が提供されている場合は、この規則による警告を抑制しても安全です。

## <a name="related-rules"></a>関連するルール
[CA1017アセンブリを ComVisibleAttribute にマークします](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>関連項目

- [要件 (相互運用のための .NET 型の)](/dotnet/framework/interop/qualifying-net-types-for-interoperation)
- [アンマネージ コードとの相互運用](/dotnet/framework/interop/index)