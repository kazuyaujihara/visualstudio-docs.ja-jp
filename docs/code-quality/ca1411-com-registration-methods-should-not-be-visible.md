---
title: CA1411:COM 登録メソッドは参照可能であることはできません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1411
- ComRegistrationMethodsShouldNotBeVisible
helpviewer_keywords:
- ComRegistrationMethodsShouldNotBeVisible
- CA1411
ms.assetid: a59f96f1-1f38-4596-b656-947df5c55311
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e9582fb6bbdbda8aefbb60e2c69d16380eec3dff
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234757"
---
# <a name="ca1411-com-registration-methods-should-not-be-visible"></a>CA1411:COM 登録メソッドは参照可能であることはできません

|||
|-|-|
|TypeName|ComRegistrationMethodsShouldNotBeVisible|
|CheckId|CA1411|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName>属性または属性でマークされたメソッドは、外部から参照できます。 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>

## <a name="rule-description"></a>規則の説明
アセンブリがコンポーネントオブジェクトモデル (COM) に登録されると、アセンブリ内の COM から参照できる各型のエントリがレジストリに追加されます。 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>属性と属性で<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>マークされたメソッドは、登録と登録解除のプロセス中にそれぞれ呼び出され、これらの型の登録/登録解除に固有のユーザーコードを実行します。 このコードは、これらのプロセスの外部では呼び出さないでください。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、メソッドのアクセシビリティをまたは`private` ( `internal` `Friend`で[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]は) に変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、規則に違反する2つのメソッドを示しています。

[!code-csharp[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/CSharp/ca1411-com-registration-methods-should-not-be-visible_1.cs)]
[!code-vb[FxCop.Interoperability.ComRegistration2#1](../code-quality/codesnippet/VisualBasic/ca1411-com-registration-methods-should-not-be-visible_1.vb)]

## <a name="related-rules"></a>関連するルール
[CA1410COM 登録メソッドは一致しなければなりません](../code-quality/ca1410-com-registration-methods-should-be-matched.md)

## <a name="see-also"></a>関連項目

- <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>
- [COM へのアセンブリの登録](/dotnet/framework/interop/registering-assemblies-with-com)
- [Regasm.exe (アセンブリ登録ツール)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)