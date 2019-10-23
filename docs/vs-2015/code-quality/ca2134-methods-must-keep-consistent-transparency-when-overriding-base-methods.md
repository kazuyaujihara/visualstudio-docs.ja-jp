---
title: 'CA2134: メソッドは、基本メソッドをオーバーライドするときに、一貫性のある透明度を維持する必要があります |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
caps.latest.revision: 11
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 96910ffc53e6c48f930232c83d87570f1bc71e00
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72608922"
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134: メソッドは、基本メソッドをオーバーライドしている場合、透過性の整合性を保つ必要がある
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MethodsMustOverrideWithConsistentTransparency|
|CheckId|CA2134|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 この規則は、<xref:System.Security.SecurityCriticalAttribute> でマークされたメソッドが、透過的または <xref:System.Security.SecuritySafeCriticalAttribute> でマークされたメソッドをオーバーライドするときに適用されます。 この規則は、透過的または <xref:System.Security.SecuritySafeCriticalAttribute> でマークされたメソッドが、<xref:System.Security.SecurityCriticalAttribute> でマークされたメソッドをオーバーライドした場合にも発生します。

 この規則は、仮想メソッドをオーバーライドする場合やインターフェイスを実装する場合に適用されます。

## <a name="rule-description"></a>規則の説明
 この規則は、継承チェーンのさらに上にあるメソッドのセキュリティアクセシビリティを変更しようとした場合に発生します。 たとえば、基底クラスの仮想メソッドが透過的またはセーフクリティカルである場合、派生クラスは透過的またはセーフクリティカルなメソッドでオーバーライドする必要があります。 逆に、仮想がセキュリティクリティカルである場合、派生クラスはセキュリティクリティカルなメソッドでそれをオーバーライドする必要があります。 インターフェイスメソッドの実装にも同じ規則が適用されます。

 透過性規則は、コードが実行時ではなく JIT コンパイルされる場合に適用されます。これにより、透過性の計算に動的な型情報が含まれなくなります。 したがって、透過性の計算結果は、動的な型に関係なく、JIT コンパイルされている静的な型からのみ特定できる必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、仮想メソッドをオーバーライドするメソッドの透明度を変更するか、仮想メソッドまたはインターフェイスメソッドの透過性に一致するようにインターフェイスを実装します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則からの警告を抑制しないでください。 この規則に違反すると、レベル2の透過性を使用するアセンブリのランタイム <xref:System.TypeLoadException> が生成されます。

## <a name="examples"></a>使用例

### <a name="code"></a>コード
 [!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2134.methodsmustoverridewithconsistenttransparency/cs/ca2134 - methodsmustoverridewithconsistenttransparency.cs#1)]

## <a name="see-also"></a>参照
 [透過的セキュリティコード、レベル2](https://msdn.microsoft.com/library/4d05610a-0da6-4f08-acea-d54c9d6143c0)
