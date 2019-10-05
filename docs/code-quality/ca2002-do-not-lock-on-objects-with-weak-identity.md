---
title: CA2002:弱い ID を伴うオブジェクト上でロックしません
ms.date: 01/31/2018
ms.topic: reference
f1_keywords:
- DoNotLockOnObjectsWithWeakIdentity
- CA2002
helpviewer_keywords:
- CA2002
- DoNotLockOnObjectsWithWeakIdentity
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: fc4504e917daeadc93963c6d6870c00515a5065a
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233161"
---
# <a name="ca2002-do-not-lock-on-objects-with-weak-identity"></a>CA2002:弱い ID を伴うオブジェクト上でロックしません

|||
|-|-|
|TypeName|DoNotLockOnObjectsWithWeakIdentity|
|CheckId|CA2002|
|カテゴリ|Microsoft.Reliability|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

スレッドが、脆弱な id を持つオブジェクトのロックを取得しようとしています。

## <a name="rule-description"></a>規則の説明

アプリケーション ドメインの境界を越えてオブジェクトに直接アクセスできる場合、そのオブジェクトの ID は不十分と表現されます。 スレッドで ID が不十分なオブジェクトをロックしようとすると、ブロックされることがあります。たとえば、異なるアプリケーション ドメインの別スレッドで、既に同じオブジェクトがロックされている場合です。

次の型には脆弱な id があり、規則によってフラグが設定されています。

- <xref:System.String>

- 値型の配列 ([整数型](/dotnet/csharp/language-reference/keywords/integral-types-table)、[浮動小数点型](/dotnet/csharp/language-reference/keywords/floating-point-types-table)、 <xref:System.Boolean>など)。

- <xref:System.MarshalByRefObject>

- <xref:System.ExecutionEngineException>

- <xref:System.OutOfMemoryException>

- <xref:System.StackOverflowException>

- <xref:System.Reflection.MemberInfo>

- <xref:System.Reflection.ParameterInfo>

- <xref:System.Threading.Thread>

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、[説明] セクションの一覧に含まれていない型のオブジェクトを使用します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。

## <a name="related-rules"></a>関連するルール

[CA2213: 破棄可能なフィールドは破棄されなければなりません](../code-quality/ca2213-disposable-fields-should-be-disposed.md)

## <a name="example"></a>例

次の例は、ルールに違反しているいくつかのオブジェクトロックを示しています。

[!code-vb[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/VisualBasic/ca2002-do-not-lock-on-objects-with-weak-identity_1.vb)]
[!code-csharp[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/CSharp/ca2002-do-not-lock-on-objects-with-weak-identity_1.cs)]

## <a name="see-also"></a>関連項目

- <xref:System.Threading.Monitor>
- <xref:System.AppDomain>
- [lock ステートメント (C#)](/dotnet/csharp/language-reference/keywords/lock-statement)
- [SyncLock ステートメント (Visual Basic)](/dotnet/visual-basic/language-reference/statements/synclock-statement)