---
title: CA2149:透過的メソッドは、ネイティブ コード内に呼び出しを行ってはならない
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2149
ms.assetid: 28951bd7-f3db-4871-99aa-bad68d1ead80
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 8e75b12b820b3ff3ac5a26f83148a49ca87c12ad
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231951"
---
# <a name="ca2149-transparent-methods-must-not-call-into-native-code"></a>CA2149:透過的メソッドは、ネイティブ コード内に呼び出しを行ってはならない

|||
|-|-|
|TypeName|TransparentMethodsMustNotCallNativeCode|
|CheckId|CA2149|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
メソッドは、P/Invoke などのメソッドスタブを介してネイティブ関数を呼び出します。

## <a name="rule-description"></a>規則の説明
この規則は、P/Invoke などを使用してネイティブコードを直接呼び出す透過的メソッドに対して適用されます。 この規則<xref:System.MethodAccessException>を違反すると、レベル2の透過性モデルのになり、レベル1の<xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A>透過性モデルのに対する完全な要求が発生します。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するに<xref:System.Security.SecurityCriticalAttribute>は、ネイティブコードを呼び出すメソッドを、属性または<xref:System.Security.SecuritySafeCriticalAttribute>属性でマークします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
[!code-csharp[FxCop.Security.CA2149.TransparentMethodsMustNotCallNativeCode#1](../code-quality/codesnippet/CSharp/ca2149-transparent-methods-must-not-call-into-native-code_1.cs)]