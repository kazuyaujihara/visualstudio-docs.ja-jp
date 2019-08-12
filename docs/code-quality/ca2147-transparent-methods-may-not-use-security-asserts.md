---
title: CA2147:透過コードは、セキュリティ アサートを使用してはならない
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- SecurityTransparentCodeShouldNotAssert
- CA2147
- CA2128
helpviewer_keywords:
- CA2128
- SecurityTransparentCodeShouldNotAssert
ms.assetid: 5d31e940-e599-4b23-9b28-1c336f8d910e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e1b56001f5a083317911edde9282b66758deb1b6
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920723"
---
# <a name="ca2147-transparent-methods-may-not-use-security-asserts"></a>CA2147:透過コードは、セキュリティ アサートを使用してはならない

|||
|-|-|
|TypeName|SecurityTransparentCodeShouldNotAssert|
|CheckId|CA2147|
|Category|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
としてマークさ<xref:System.Security.SecurityTransparentAttribute>れているコードには、アサートに必要なアクセス許可が付与されていません。

## <a name="rule-description"></a>規則の説明
このルールは、アセンブリ内のすべてのメソッドと型を分析します。これは、透過的に 100%、transparent/critical が混在<xref:System.Security.CodeAccessPermission.Assert%2A>しています。また、の宣言型または命令型の使用にフラグを加えます。

実行時に、透過的な<xref:System.Security.CodeAccessPermission.Assert%2A>コードからを呼び出すと<xref:System.InvalidOperationException> 、がスローされます。 これは、100% の透過アセンブリでも、メソッドまたは型が透過的に宣言されているが、宣言型または命令型のアサートを含む、透過的またはクリティカルなアセンブリでも発生する可能性があります。

.NET Framework 2.0 では、*透明性*という名前の機能が導入されました。 個々のメソッド、フィールド、インターフェイス、クラス、および型は、透過的または重大にすることができます。

透過的なコードでは、セキュリティ特権を昇格することはできません。 したがって、このメソッドに付与または要求されるアクセス許可は、コードを通じて呼び出し元またはホストアプリケーションドメインに自動的に渡されます。 昇格の例として`unsafe`は、アサート、linkdemand、SuppressUnmanagedCode、コードなどがあります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この問題を解決するには、アサート<xref:System.Security.SecurityCriticalAttribute>を呼び出すコードをでマークするか、アサートを削除します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則からのメッセージを抑制しないでください。

## <a name="example"></a>例
このコードは、が`SecurityTestClass`透過的`Assert`な場合に、メソッドがを<xref:System.InvalidOperationException>スローした場合に失敗します。

[!code-csharp[FxCop.Security.CA2147.TransparentMethodsMustNotUseSecurityAsserts#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_1.cs)]

## <a name="example"></a>例
1つの方法として、次の例の SecurityTransparentMethod メソッドをコードレビューする方法があります。また、メソッドが昇格に対して安全であると見なされる場合は、SecurityTransparentMethod に secure-critical とマークします。 そのためには、メソッドに対して、アサートの下でメソッド内で発生するすべての呼び出しと共に、詳細、完全、およびエラーのないセキュリティ監査を実行する必要があります。

[!code-csharp[FxCop.Security.SecurityTransparentCode2#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_2.cs)]

もう1つの方法として、コードからアサートを削除し、後続のファイル i/o のアクセス許可要求を SecurityTransparentMethod を超えて呼び出し元に渡すこともできます。 これにより、セキュリティチェックが有効になります。 この場合、アクセス許可要求は呼び出し元またはアプリケーションドメインにフローするため、セキュリティ監査は必要ありません。 アクセス許可の要求は、セキュリティポリシー、ホスト環境、およびコードソースのアクセス許可の付与によって厳密に制御されます。

## <a name="see-also"></a>関連項目
[セキュリティの警告](../code-quality/security-warnings.md)