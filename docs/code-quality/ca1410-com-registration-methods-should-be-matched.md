---
title: CA1410:COM 登録メソッドは一致しなければなりません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
helpviewer_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a424e3c884d47b7deb848b418fbf0f3344d6c379
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "66714732"
---
# <a name="ca1410-com-registration-methods-should-be-matched"></a>CA1410:COM 登録メソッドは一致しなければなりません

|||
|-|-|
|TypeName|ComRegistrationMethodsShouldBeMatched|
|CheckId|CA1410|
|カテゴリ|Microsoft.Interoperability|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

マークされているメソッドを宣言する型、<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName>属性しますが、でマークされているメソッドを宣言しません、<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>属性、またはその逆です。

## <a name="rule-description"></a>規則の説明

コンポーネント オブジェクト モデル (COM) クライアントに .NET 型を作成する、型を登録する必要がありますまずします。 可能な場合でマークされているメソッド、<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>属性は、ユーザー指定のコードを実行する登録プロセス中に呼び出されます。 マークされている対応するメソッド、<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>属性は、登録メソッドの操作を反転する登録解除プロセス中に呼び出されます。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、対応する登録または登録解除メソッドを追加します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告は抑制しないでください。

## <a name="example"></a>例

次の例では、規則に違反する型を示します。 コメント付きのコードでは、違反の修正プログラムを示します。

[!code-csharp[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/CSharp/ca1410-com-registration-methods-should-be-matched_1.cs)]
[!code-vb[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/VisualBasic/ca1410-com-registration-methods-should-be-matched_1.vb)]

## <a name="related-rules"></a>関連するルール

[CA1411:COM 登録メソッドを表示することはできません。](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)

## <a name="see-also"></a>関連項目

- <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>
- [COM にアセンブリを登録します。](/dotnet/framework/interop/registering-assemblies-with-com)
- [Regasm.exe (アセンブリ登録ツール)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)