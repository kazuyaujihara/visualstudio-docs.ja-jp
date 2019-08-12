---
title: CA2124:脆弱性のある finally 句を外側の try でラップします
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
helpviewer_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
ms.assetid: 82efd224-9e60-4b88-a0f5-dfabcc49a254
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c75c7c240f694b18caacefc0f9b1ee07f54faf36
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920799"
---
# <a name="ca2124-wrap-vulnerable-finally-clauses-in-outer-try"></a>CA2124:脆弱性のある finally 句を外側の try でラップします

|||
|-|-|
|TypeName|WrapVulnerableFinallyClausesInOuterTry|
|CheckId|CA2124|
|Category|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
.NET Framework のバージョン1.0 および1.1 では、パブリックメソッドまたはプロテクトメソッドに`try` `finally`ブロックが含まれてい/ `catch` /ます。 ブロックがセキュリティ状態をリセットしているように見えます`finally`が、ブロックで囲まれていません。 `finally`

## <a name="rule-description"></a>規則の説明
このルールは`try` 、コールスタックに存在する悪意のある例外フィルターに対して脆弱である可能性がある .NET Framework のバージョン1.0 および1.1 を対象とするコード内のブロックを検索/ `finally`します。 偽装などの機密性の高い操作が try ブロックで発生し、例外がスローされた場合は、ブロック`finally`の前にフィルターを実行できます。 偽装の例では、これは、フィルターが権限を借用したユーザーとして実行されることを意味します。 現在、フィルターは Visual Basic のみで実装できます。

> [!NOTE]
> .NET Framework のバージョン2.0 以降では、リセットがメソッド内で直接`try`発生した場合、ランタイムは悪意のある例外フィルターからブロックを/  / `catch` `finally`自動的に保護します。例外ブロックを格納します。

## <a name="how-to-fix-violations"></a>違反の修正方法
ラップ`try` されて`finally`いないを外側の try ブロックに配置します。 / 次の2番目の例を参照してください。 これにより`finally` 、は、フィルターコードの前にを強制的に実行します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="pseudo-code-example"></a>擬似コードの例

### <a name="description"></a>説明

次の擬似コードでは、このルールにより検出されたパターンを示しています。

```csharp
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

次の擬似コードは、コードを保護し、この規則を満たすために使用できるパターンを示しています。

```csharp
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