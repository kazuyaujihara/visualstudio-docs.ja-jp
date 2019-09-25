---
title: CA1064:例外は public として設定する必要があります
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1064
- ExceptionsShouldBePublic
helpviewer_keywords:
- ExceptionsShouldBePublic
- CA1064
ms.assetid: 83eb224c-2456-4368-acf4-3b3378e67759
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0ffc12d8d047be1bb13fcac133a61b047152ce3d
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235327"
---
# <a name="ca1064-exceptions-should-be-public"></a>CA1064:例外は public として設定する必要があります

|||
|-|-|
|TypeName|ExceptionsShouldBePublic|
|CheckId|CA1064|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
パブリックでない例外は、 <xref:System.Exception> <xref:System.SystemException>、、または<xref:System.ApplicationException>から直接派生します。

## <a name="rule-description"></a>規則の説明
内部例外は、独自の内部スコープ内でのみ表示されます。 内部スコープの外側にある例外は、基本例外を使用しなければキャッチできません。 場合、内部例外から継承<xref:System.Exception>、 <xref:System.SystemException>、または<xref:System.ApplicationException>、外部のコードには、例外の処理方法を把握するための十分な情報はありません。

ただし、後で内部例外のベースとして使用されるパブリック例外がコードにある場合は、さらに詳細なコードが基本例外でインテリジェントな処理を実行できると想定することが妥当です。 パブリック例外には、、 <xref:System.Exception> <xref:System.SystemException>、または<xref:System.ApplicationException>で提供されるものよりも多くの情報が含まれます。

## <a name="how-to-fix-violations"></a>違反の修正方法
例外をパブリックにするか、、 <xref:System.Exception> <xref:System.SystemException>、または<xref:System.ApplicationException>ではないパブリック例外から内部例外を派生させます。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
常にプライベート例外が独自の内部スコープ内でキャッチされる場合は、この規則からのメッセージを抑制します。

## <a name="example"></a>例
この規則は、最初の例のメソッドである FirstCustomException で、例外クラスが例外から直接派生し、内部であるために発生します。 このルールは、クラスは例外から直接派生していますが、クラスは public として宣言されているため、このクラスでは起動されません。 3番目のクラスは、、 <xref:System.Exception?displayProperty=fullName> <xref:System.SystemException?displayProperty=fullName>、または<xref:System.ApplicationException?displayProperty=fullName>から直接派生していないため、ルールを起動しません。

[!code-csharp[FxCop.Design.ExceptionsShouldBePublic.CA1064#1](../code-quality/codesnippet/CSharp/ca1064-exceptions-should-be-public_1.cs)]
