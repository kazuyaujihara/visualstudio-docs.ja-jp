---
title: 'CA2118: SuppressUnmanagedCodeSecurityAttribute usage | を確認します。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2118
- ReviewSuppressUnmanagedCodeSecurityUsage
helpviewer_keywords:
- ReviewSuppressUnmanagedCodeSecurityUsage
- CA2118
ms.assetid: 4cb8d2fc-4e44-4dc3-9b74-7f5838827d41
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: bb7404d9add159f182ae44b22444dded1aafca20
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72658647"
---
# <a name="ca2118-review-suppressunmanagedcodesecurityattribute-usage"></a>CA2118: SuppressUnmanagedCodeSecurityAttribute の使用法をレビューします
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ReviewSuppressUnmanagedCodeSecurityUsage|
|CheckId|CA2118|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 パブリックまたはプロテクトの型またはメンバーには、<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> 属性があります。

## <a name="rule-description"></a>規則の説明
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> は、COM 相互運用機能またはプラットフォーム呼び出しを使用してアンマネージコードを実行するメンバーの既定のセキュリティシステムの動作を変更します。 一般に、システムは、アンマネージコードのアクセス許可の[データとモデリング](https://msdn.microsoft.com/library/8c37635d-e2c1-4b64-a258-61d9e87405e6)を行います。 この要求は、メンバーが呼び出されるたびに実行時に発生し、呼び出し履歴内のすべての呼び出し元に対してアクセス許可があるかどうかをチェックします。 属性が存在する場合、システムはアクセス許可の[リンク確認要求](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)を行います。呼び出し元が JIT でコンパイルされると、直接の呼び出し元のアクセス許可がチェックされます。

 この属性は、主にパフォーマンスを向上するために使用されますが、パフォーマンスが向上するとセキュリティ上のリスクも高くなります。 ネイティブメソッドを呼び出すパブリックメンバーに属性を配置した場合、呼び出し履歴 (直前の呼び出し元を除く) 内の呼び出し元は、アンマネージコードを実行するためのアンマネージコードのアクセス許可を必要としません。 パブリックメンバーのアクションと入力処理によっては、信頼できない呼び出し元が、信頼できるコードに通常制限されている機能にアクセスする可能性があります。

 @No__t_0 は、呼び出し元が現在のプロセスのアドレス空間に直接アクセスできないようにするために、セキュリティチェックに依存しています。 この属性は通常のセキュリティをバイパスするため、プロセスのメモリの読み取りや書き込みに使用できる場合は、コードに重大な脅威が生じます。 リスクは、意図的にプロセスメモリへのアクセスを提供するメソッドに限定されないことに注意してください。また、この情報は、悪意のあるコードが何らかの方法でアクセスできるようなシナリオにも存在します。たとえば、驚くべき、形式が正しくない、または無効な入力を提供します。

 既定のセキュリティポリシーでは、アセンブリがローカルコンピューターから実行されているか、次のいずれかのグループのメンバーでない限り、アンマネージコードのアクセス許可がアセンブリに付与されません。

- マイコンピューターゾーンコードグループ

- Microsoft 厳密な名前のコードグループ

- ECMA 厳密名コードグループ

## <a name="how-to-fix-violations"></a>違反の修正方法
 コードを慎重に確認し、この属性が絶対に必要であることを確認します。 マネージコードセキュリティについてよく知らない場合、またはこの属性を使用した場合のセキュリティへの影響を理解していない場合は、コードから削除します。 属性が必要な場合は、呼び出し元が悪意のあるコードを使用できないようにする必要があります。 コードにアンマネージコードを実行するためのアクセス許可がない場合、この属性は無効であり、削除する必要があります。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則からの警告を安全に抑制するには、コードからネイティブの操作または破壊的な方法で使用できるリソースへのアクセスが提供されていないことを確認する必要があります。

## <a name="example"></a>例
 次の例は、規則に違反しています。

 [!code-csharp[FxCop.Security.TypesDoNotSuppress#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TypesDoNotSuppress/cs/FxCop.Security.TypesDoNotSuppress.cs#1)]

## <a name="example"></a>例
 次の例では、`DoWork` メソッドによって、`FormatHardDisk` プラットフォーム呼び出しメソッドへのパブリックにアクセスできるコードパスが提供されます。

 [!code-csharp[FxCop.Security.PInvokeAndSuppress#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.PInvokeAndSuppress/cs/FxCop.Security.PInvokeAndSuppress.cs#1)]

## <a name="example"></a>例
 次の例では、パブリックメソッド `DoDangerousThing` に違反が発生します。 違反を解決するには、`DoDangerousThing` をプライベートにする必要があります。また、`DoWork` メソッドに示されているように、セキュリティ要求によって保護されたパブリックメソッドを使用してアクセスする必要があります。

 [!code-csharp[FxCop.Security.TypeInvokeAndSuppress#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TypeInvokeAndSuppress/cs/FxCop.Security.TypeInvokeAndSuppress.cs#1)]

## <a name="see-also"></a>参照
 セキュリティ[で保護されたコーディングガイドライン](https://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)の <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName>[セキュリティ最適化](https://msdn.microsoft.com/cf255069-d85d-4de3-914a-e4625215a7c0)[データとモデリングの](https://msdn.microsoft.com/library/8c37635d-e2c1-4b64-a258-61d9e87405e6)[リンク確認要求](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)
