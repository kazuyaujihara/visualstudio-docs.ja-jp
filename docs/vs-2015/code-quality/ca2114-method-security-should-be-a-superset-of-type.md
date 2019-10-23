---
title: 'CA2114: メソッドのセキュリティは、型 | のスーパーセットである必要がありますMicrosoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MethodSecurityShouldBeASupersetOfType
- CA2114
helpviewer_keywords:
- CA2114
- MethodSecurityShouldBeASupersetOfType
ms.assetid: 663f7aa4-8be5-4bd5-be92-4e9444f07077
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 1adc8f610644d736bc4546d8299457ba0234a1d9
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72658667"
---
# <a name="ca2114-method-security-should-be-a-superset-of-type"></a>CA2114: メソッドのセキュリティは型のスーパーセットにします
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MethodSecurityShouldBeASupersetOfType|
|CheckId|CA2114|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 型に宣言セキュリティがあり、そのメソッドの1つに同じセキュリティアクションの宣言セキュリティがあり、セキュリティアクションが[リンク](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)確認要求または[継承要求](https://msdn.microsoft.com/28b9adbb-8f08-4f10-b856-dbf59eb932d9)ではなく、型によってチェックされるアクセス許可が、のサブセットではありません。メソッドによって確認されるアクセス許可。

## <a name="rule-description"></a>規則の説明
 メソッドは、同じアクションに対して、メソッドレベルと型レベルの宣言セキュリティの両方を持つことはできません。 2つのチェックは結合されません。メソッドレベルの要求だけが適用されます。 たとえば、型が `X` アクセス許可を要求し、そのいずれかのメソッドが `Y` アクセス許可を要求する場合、コードには、メソッドを実行するためのアクセス許可 `X` が必要ありません。

## <a name="how-to-fix-violations"></a>違反の修正方法
 コードを確認して、両方のアクションが必要であることを確認します。 両方のアクションが必要な場合は、メソッドレベルのアクションに、型レベルで指定されたセキュリティが含まれていることを確認してください。 たとえば、型が `X` アクセス許可を要求し、そのメソッドが `Y` アクセス許可も要求する必要がある場合、メソッドは `X` と `Y` を明示的に要求する必要があります。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 メソッドが型によって指定されたセキュリティを必要としない場合は、この規則による警告を抑制しても安全です。 ただし、これは通常のシナリオではなく、慎重な設計レビューが必要であることを示している可能性があります。

## <a name="example"></a>例
 次の例では、環境のアクセス許可を使用して、この規則に違反する危険性を示します。 この例では、アプリケーションコードは、型に必要なアクセス許可を拒否する前に、セキュリティで保護された型のインスタンスを作成します。 実際の脅威のシナリオでは、アプリケーションでオブジェクトのインスタンスを取得する別の方法が必要になります。

 次の例では、ライブラリは、型に対する書き込みアクセス許可と、メソッドに対する読み取りアクセス許可を要求します。

 [!code-csharp[FxCop.Security.MethodLevelSecurity#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.MethodLevelSecurity/cs/FxCop.Security.MethodLevelSecurity.cs#1)]

## <a name="example"></a>例
 次のアプリケーションコードは、型レベルのセキュリティ要件を満たしていない場合でも、メソッドを呼び出すことによって、ライブラリの脆弱性を示しています。

 [!code-csharp[FxCop.Security.TestMethodLevelSecurity#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TestMethodLevelSecurity/cs/FxCop.Security.TestMethodLevelSecurity.cs#1)]

 この例を実行すると、次の出力が生成されます。

 **[すべてのアクセス許可] 個人情報: 6/16/1964 12:00:00 am** 
 **[書き込みアクセス許可がありません (種類別に要求)] 個人情報: 6/16/1964 12:00:00 AM** 
 **[読み取りアクセス許可がない (メソッドによって要求されました)] は個人用にアクセスできませんでした情報: 要求が失敗しました。**
## <a name="see-also"></a>参照
 [セキュリティで保護されたコーディングガイドライン](https://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)の[継承要求](https://msdn.microsoft.com/28b9adbb-8f08-4f10-b856-dbf59eb932d9)の[リンク要求](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)[データとモデリング](https://msdn.microsoft.com/library/8c37635d-e2c1-4b64-a258-61d9e87405e6)
