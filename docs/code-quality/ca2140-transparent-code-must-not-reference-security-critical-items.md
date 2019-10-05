---
title: CA2140:透過的コードは、セキュリティ上重要な項目を参照してはならない
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2129
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2140
helpviewer_keywords:
- CA2140
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2129
ms.assetid: 251a12da-0557-47f5-a4f7-0229d590ae7b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d4f02938aed7456762f1ef51da716b6b96bdf437
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71232148"
---
# <a name="ca2140-transparent-code-must-not-reference-security-critical-items"></a>CA2140:透過的コードは、セキュリティ上重要な項目を参照してはならない

|||
|-|-|
|TypeName|TransparentMethodsMustNotReferenceCriticalCode|
|CheckId|CA2140|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

透過的な方法:

- セキュリティクリティカルなセキュリティ例外の種類を処理します

- セキュリティクリティカルな型としてマークされているパラメーターがある

- には、セキュリティクリティカルな制約を持つジェネリックパラメーターがあります

- セキュリティクリティカルな型のローカル変数を持つ

- セキュリティクリティカルとしてマークされている型を参照します

- セキュリティクリティカルとしてマークされているメソッドを呼び出します

- セキュリティクリティカルとしてマークされているフィールドを参照する

- セキュリティクリティカルとしてマークされている型を返します

## <a name="rule-description"></a>規則の説明

<xref:System.Security.SecurityCriticalAttribute>属性でマークされたコード要素は、セキュリティクリティカルです。 透過的なメソッドでセキュリティ上重要な要素を使用することはできません。 透過型がセキュリティクリティカルな型<xref:System.TypeAccessException> <xref:System.MethodAccessException>を使用しようとすると、 <xref:System.FieldAccessException> 、、またはが発生します。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、次のいずれかの操作を行います。

- セキュリティクリティカルなコードを使用するコード要素を<xref:System.Security.SecurityCriticalAttribute>属性でマークします。

     \- または

- セキュリティクリティカルとマークされているコード要素から<xref:System.Security.SecuritySafeCriticalAttribute> <xref:System.Security.SecurityTransparentAttribute> 属性を削除し、代わりに属性または属性で<xref:System.Security.SecurityCriticalAttribute>マークします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。

## <a name="example"></a>例

次の例では、透過的メソッドは、セキュリティクリティカルなジェネリックコレクション、セキュリティクリティカルフィールド、およびセキュリティクリティカルなメソッドを参照しようとします。

[!code-csharp[FxCop.Security.CA2140.TransparentMethodsMustNotReferenceCriticalCode#1](../code-quality/codesnippet/CSharp/ca2140-transparent-code-must-not-reference-security-critical-items_1.cs)]

## <a name="see-also"></a>関連項目

- <xref:System.Security.SecurityTransparentAttribute>
- <xref:System.Security.SecurityCriticalAttribute>
- <xref:System.Security.SecurityTransparentAttribute>
- <xref:System.Security.SecurityTreatAsSafeAttribute>
- <xref:System.Security?displayProperty=fullName>