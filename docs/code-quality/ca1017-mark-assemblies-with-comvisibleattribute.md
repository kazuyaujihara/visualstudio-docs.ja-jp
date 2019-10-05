---
title: CA1017:アセンブリに ComVisibleAttribute を設定します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1017
- MarkAssembliesWithComVisible
helpviewer_keywords:
- MarkAssembliesWithComVisible
- CA1017
ms.assetid: 4842cb49-8dd8-4e5d-a2d6-ceeaf6c6cf8e
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 073332738a01cb299b2b185c6fca20131222f981
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236254"
---
# <a name="ca1017-mark-assemblies-with-comvisibleattribute"></a>CA1017:アセンブリに ComVisibleAttribute を設定します

|||
|-|-|
|TypeName|MarkAssembliesWithComVisible|
|CheckId|CA1017|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
アセンブリに<xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName>属性が適用されていません。

## <a name="rule-description"></a>規則の説明
属性<xref:System.Runtime.InteropServices.ComVisibleAttribute>は、COM クライアントがマネージコードにアクセスする方法を決定します。 アセンブリで COM の参照範囲を明示することをお勧めします。 COM の可視性は、アセンブリ全体に対して設定し、個々の型および型のメンバーに対してオーバーライドできます。 属性が存在しない場合、アセンブリの内容は COM クライアントから参照できます。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、属性をアセンブリに追加します。 アセンブリが COM クライアントに表示されないようにするには、属性を適用し、その値`false`をに設定します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。 アセンブリを表示する場合は、属性を適用し、その値をに`true`設定します。

## <a name="example"></a>例
次の例は、 <xref:System.Runtime.InteropServices.ComVisibleAttribute>属性が COM クライアントに表示されないようにするために属性が適用されているアセンブリを示しています。

[!code-cpp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CPP/ca1017-mark-assemblies-with-comvisibleattribute_1.cpp)]
[!code-vb[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/VisualBasic/ca1017-mark-assemblies-with-comvisibleattribute_1.vb)]
[!code-csharp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CSharp/ca1017-mark-assemblies-with-comvisibleattribute_1.cs)]

## <a name="see-also"></a>関連項目

- [アンマネージ コードとの相互運用](/dotnet/framework/interop/index)
- [要件 (相互運用のための .NET 型の)](/dotnet/framework/interop/qualifying-net-types-for-interoperation)