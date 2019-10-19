---
title: 'CA2124: 脆弱性のある finally 句を外側の try | でラップします。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
helpviewer_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
ms.assetid: 82efd224-9e60-4b88-a0f5-dfabcc49a254
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 7a2a296f5dd3680209c14849b5bd863c01e6351d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72660245"
---
# <a name="ca2124-wrap-vulnerable-finally-clauses-in-outer-try"></a>CA2124: 脆弱性のある finally 句の外側を try ブロックでラップします
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|WrapVulnerableFinallyClausesInOuterTry|
|CheckId|CA2124|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 @No__t_0 のバージョン1.0 および1.1 では、パブリックメソッドまたはプロテクトメソッドに `try` / `catch` / `finally` ブロックが含まれています。 @No__t_0 ブロックがセキュリティ状態をリセットしているため、`finally` ブロックで囲まれていません。

## <a name="rule-description"></a>規則の説明
 このルールは、コールスタックに存在する悪意のある例外フィルターに対して脆弱である可能性がある [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] のバージョン1.0 および1.1 を対象とするコード内の / `finally` ブロック `try` を検索します。 偽装などの機密性の高い操作が try ブロックで発生し、例外がスローされた場合、フィルターは `finally` ブロックの前に実行できます。 偽装の例では、これは、フィルターが権限を借用したユーザーとして実行されることを意味します。 現在、フィルターは Visual Basic のみで実装できます。

> [!WARNING]
> @No__t_0 のバージョン2.0 以降では、例外ブロックを含むメソッド内でリセットが直接行われた場合、ランタイムは、悪意のある例外フィルターから `catch` /  `finally` ブロックの `try` / を自動的に保護します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 ラップされていない `try` / `finally` を外側の try ブロックに配置します。 次の2番目の例を参照してください。 これにより、フィルターコードの前に `finally` が強制的に実行されます。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="pseudo-code-example"></a>擬似コードの例

### <a name="description"></a>説明
 次の擬似コードでは、このルールにより検出されたパターンを示しています。

### <a name="code"></a>コード

```
try {
   // Do some work.
   Impersonator imp = new Impersonator("John Doe");
   imp.AddToCreditCardBalance(100);
}
finally {
   // Reset security state.
   imp.Revert();
}
```

## <a name="example"></a>例
 次の擬似コードは、コードを保護し、この規則を満たすために使用できるパターンを示しています。

```
try {
     try {
        // Do some work.
     }
     finally {
        // Reset security state.
     }
}
catch()
{
    throw;
}
```
