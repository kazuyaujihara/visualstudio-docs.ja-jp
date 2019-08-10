---
title: CA2116:APTCA メソッドは APTCA メソッドのみを呼び出すことができます
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
helpviewer_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
ms.assetid: 8b91637e-891f-4dde-857b-bf8012270ec4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f55c48583e47a4602f33d69799d1d86a6c9c3e56
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921155"
---
# <a name="ca2116-aptca-methods-should-only-call-aptca-methods"></a>CA2116:APTCA メソッドは APTCA メソッドのみを呼び出すことができます

|||
|-|-|
|TypeName|AptcaMethodsShouldOnlyCallAptcaMethods|
|CheckId|CA2116|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

<xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName>属性を持つアセンブリ内のメソッドが、属性を持たないアセンブリ内のメソッドを呼び出しています。

## <a name="rule-description"></a>規則の説明

既定では、厳密な名前を持つアセンブリ内のパブリックメソッドまたはプロテクトメソッドは、完全信頼の[リンク確認要求](/dotnet/framework/misc/link-demands)によって暗黙的に保護されます。完全に信頼された呼び出し元だけが、厳密な名前付きアセンブリにアクセスできます。 (APTCA) 属性でマークさ<xref:System.Security.AllowPartiallyTrustedCallersAttribute>れた厳密な名前付きのアセンブリには、この保護はありません。 属性は、リンク確認要求を無効にし、イントラネットまたはインターネットからコードを実行するなど、完全に信頼されていない呼び出し元がアセンブリにアクセスできるようにします。

APTCA 属性が完全に信頼されたアセンブリに存在し、部分的に信頼された呼び出し元を許可しない別のアセンブリのコードをアセンブリが実行すると、セキュリティ上の脆弱性が発生する可能性があります。 2つの`M1`メソッド`M2`があり、次の条件を満たす場合、悪意`M1`のある呼び出し元はメソッドを使用して`M2`、を保護する暗黙的な完全信頼リンク要求をバイパスできます。

- `M1`は、APTCA 属性を持つ、完全に信頼されたアセンブリで宣言されたパブリックメソッドです。

- `M1`のアセンブリの`M2`外部`M1`でメソッドを呼び出します。

- `M2`のアセンブリには APTCA 属性が含まれていないため、部分的に信頼されている呼び出し元の代わりにまたはによって実行することはできません。

部分的`M1`に信頼さ`X`れた呼び出し`M1`元はメソッドを`M2`呼び出して、を呼び出すことができます。 に`M2`は APTCA 属性がないため、直接の呼び出し元`M1`() は完全信頼のリンク確認要求を満たす必要があります。`M1`は完全に信頼されているため、このチェックを満たします。 セキュリティ上のリスクは`X` 、信頼されていない呼び出し元から`M2`保護されるリンク確認要求に、が関与しないためです。 そのため、APTCA 属性を持つメソッドは、属性を持たないメソッドを呼び出すことはできません。

## <a name="how-to-fix-violations"></a>違反の修正方法
APCTA 属性が必要な場合は、要求を使用して、完全信頼アセンブリを呼び出すメソッドを保護します。 必要なアクセス許可は、メソッドによって公開される機能によって異なります。 可能であれば、完全信頼の要求によってメソッドを保護し、基になる機能が部分的に信頼された呼び出し元に公開されないようにします。 これが不可能な場合は、公開されている機能を効果的に保護するアクセス許可のセットを選択します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則からの警告を安全に抑制するには、メソッドによって公開されている機能が、破壊的な方法で使用できる機密情報、操作、またはリソースに直接または間接的にアクセスすることを、呼び出し元に許可しないようにする必要があります。

## <a name="example-1"></a>例 1
次の例では、2つのアセンブリとテストアプリケーションを使用して、この規則によって検出されたセキュリティの脆弱性を示しています。 最初のアセンブリには APTCA 属性がなく、部分的に信頼された呼び出し元 (前の`M2`説明ではによって表されます) からアクセスできないようにする必要があります。

[!code-csharp[FxCop.Security.NoAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_1.cs)]

## <a name="example-2"></a>例 2
2番目のアセンブリは完全に信頼されており、 `M1`部分的に信頼された呼び出し元を許可します (前の説明ではに示されています)。

[!code-csharp[FxCop.Security.YesAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_2.cs)]

## <a name="example-3"></a>例 3
(前の説明ので`X`示されている) テストアプリケーションは、部分的に信頼されています。

[!code-csharp[FxCop.Security.TestAptcaMethods#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_3.cs)]

この例を実行すると、次の出力が生成されます。

```txt
Demand for full trust:Request failed.
ClassRequiringFullTrust.DoWork was called.
```

## <a name="related-rules"></a>関連するルール

- [CA2117APTCA 型は APTCA 基本型のみを拡張する必要があります](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)

## <a name="see-also"></a>関連項目

- [安全なコーディングのガイドライン](/dotnet/standard/security/secure-coding-guidelines)
- [部分信頼コードからのライブラリの使用](/dotnet/framework/misc/using-libraries-from-partially-trusted-code)
- [リンク確認要求](/dotnet/framework/misc/link-demands)
- [データとモデリング](/dotnet/framework/data/index)