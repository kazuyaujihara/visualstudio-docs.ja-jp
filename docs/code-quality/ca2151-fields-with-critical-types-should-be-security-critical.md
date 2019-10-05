---
title: CA2151:クリティカル型のフィールドはセキュリティ クリティカルである必要があります
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 09db9d25-7d58-4725-a252-4a07baadf046
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 46cb99f00bbbd9969899121f82ba591980b5b288
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231919"
---
# <a name="ca2151-fields-with-critical-types-should-be-security-critical"></a>CA2151:クリティカル型のフィールドはセキュリティ クリティカルである必要があります

|||
|-|-|
|TypeName||
|CheckId|CA2151|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

透過的セキュリティ フィールドまたはセーフ クリティカル フィールドが宣言されました。 その型は、セキュリティ クリティカルとして指定されています。 次に例を示します。

```csharp
[assembly: AllowPartiallyTrustedCallers]

   [SecurityCritical]
   class Type1 { } // Security Critical type

   class Type2 // Security transparent type
   {
      Type1 m_field; // CA2151, transparent field of critical type
   }
```

この例では、`m_field` はセキュリティ クリティカルな型の透過的セキュリティ フィールドです。

## <a name="rule-description"></a>規則の説明

セキュリティ クリティカルな型を使用するには、型を参照するコードがセキュリティ クリティカルであるか、セキュリティ セーフ クリティカルである必要があります。 これは、参照が間接的である場合にも当てはまります。 たとえば、クリティカルな型を持つ透過的フィールドを参照する場合、コードはセキュリティ クリティカルであるか、セキュリティ セーフである必要があります。 そのため、透過的セキュリティまたはセキュリティ セーフ クリティカルなフィールドが存在すると、透過的なコードはこのフィールドにアクセスできないので、紛らわしくなります。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、フィールド<xref:System.Security.SecurityCriticalAttribute>に属性を設定するか、フィールドによって参照される型をセキュリティ透過的または安全クリティカルにします。

```csharp
// Fix 1: Make the referencing field security critical
[assembly: AllowPartiallyTrustedCallers]

   [SecurityCritical]
   class Type1 { } // Security Critical type

   class Type2 // Security transparent type
   {
      [SecurityCritical]
      Type1 m_field; // Fixed: critical type, critical field
   }

// Fix 2: Make the referencing field security critical
[assembly: AllowPartiallyTrustedCallers]

   class Type1 { } // Type1 is now transparent

   class Type2 // Security transparent type
   {
      [SecurityCritical]
      Type1 m_field; // Fixed: critical type, critical field
   }
```

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。

### <a name="code"></a>コード

[!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../code-quality/codesnippet/CSharp/ca2151-fields-with-critical-types-should-be-security-critical_1.cs)]