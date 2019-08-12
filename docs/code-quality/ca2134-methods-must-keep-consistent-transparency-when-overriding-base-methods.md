---
title: CA2134:メソッドは、基本メソッドをオーバーライドしている場合、透過性の整合性を保つ必要がある
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8ca28f364307d4a2b73235bc6541cb8aa01abd56
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920656"
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134:メソッドは、基本メソッドをオーバーライドしている場合、透過性の整合性を保つ必要がある

|||
|-|-|
|TypeName|MethodsMustOverrideWithConsistentTransparency|
|CheckId|CA2134|
|Category|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
この規則は、 <xref:System.Security.SecurityCriticalAttribute>でマークされたメソッドが透過的または<xref:System.Security.SecuritySafeCriticalAttribute>でマークされたメソッドをオーバーライドするときに適用されます。 この規則は、透過的またはで<xref:System.Security.SecuritySafeCriticalAttribute>マークされたメソッドが、 <xref:System.Security.SecurityCriticalAttribute>でマークされたメソッドをオーバーライドした場合にも発生します。

この規則は、仮想メソッドをオーバーライドする場合やインターフェイスを実装する場合に適用されます。

## <a name="rule-description"></a>規則の説明
この規則は、継承チェーンのさらに上にあるメソッドのセキュリティアクセシビリティを変更しようとした場合に発生します。 たとえば、基底クラスの仮想メソッドが透過的またはセーフクリティカルである場合、派生クラスは透過的またはセーフクリティカルなメソッドでオーバーライドする必要があります。 逆に、仮想がセキュリティクリティカルである場合、派生クラスはセキュリティクリティカルなメソッドでそれをオーバーライドする必要があります。 インターフェイスメソッドの実装にも同じ規則が適用されます。

透過性規則は、コードが実行時ではなく JIT コンパイルされる場合に適用されます。これにより、透過性の計算に動的な型情報が含まれなくなります。 したがって、透過性の計算結果は、動的な型に関係なく、JIT コンパイルされている静的な型からのみ特定できる必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、仮想メソッドをオーバーライドするメソッドの透明度を変更するか、仮想メソッドまたはインターフェイスメソッドの透過性に一致するようにインターフェイスを実装します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則からの警告を抑制しないでください。 この規則を違反すると、レベル 2 <xref:System.TypeLoadException>の透過性を使用するアセンブリのランタイムが生成されます。

## <a name="examples"></a>使用例

### <a name="code"></a>コード
[!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods_1.cs)]

## <a name="see-also"></a>関連項目
[透過的セキュリティコード、レベル2](/dotnet/framework/misc/security-transparent-code-level-2)