---
title: CA1404:P/Invoke の直後に GetLastError を呼び出します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
helpviewer_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
ms.assetid: 52ae9eff-50f9-4b2f-8039-ca7e49fba88e
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: ab789e578dd8603f604cdb00aa5d236250d13670
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235048"
---
# <a name="ca1404-call-getlasterror-immediately-after-pinvoke"></a>CA1404:P/Invoke の直後に GetLastError を呼び出します

|||
|-|-|
|TypeName|CallGetLastErrorImmediatelyAfterPInvoke|
|CheckId|CA1404|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

<xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A?displayProperty=fullName>メソッドまたは同等の Win32 `GetLastError`関数への呼び出しが行われ、その直前の呼び出しがプラットフォーム呼び出しメソッドになりません。

## <a name="rule-description"></a>規則の説明
プラットフォーム呼び出しメソッドはアンマネージコードに`Declare` [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]アクセスし、または<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>属性のキーワードを使用して定義されます。 一般に、エラーが発生した場合、 `SetLastError`アンマネージ関数は Win32 関数を呼び出して、エラーに関連付けられているエラーコードを設定します。 失敗した関数の呼び出し元は、 `GetLastError` Win32 関数を呼び出してエラーコードを取得し、エラーの原因を特定します。 エラーコードはスレッド単位で管理され、の次の呼び出し`SetLastError`によって上書きされます。 失敗したプラットフォーム呼び出しメソッドを呼び出した後、マネージコードは<xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>メソッドを呼び出してエラーコードを取得できます。 エラーコードは、他のマネージクラスライブラリメソッドからの内部呼び出しによって上書き`GetLastError`さ<xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>れる可能性があるため、またはメソッドは、プラットフォーム呼び出しメソッドの呼び出しの直後に呼び出す必要があります。

この規則は、プラットフォーム呼び出しメソッドの呼び出しと<xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>の呼び出しの間に、次のマネージメンバーが発生した場合に、その呼び出しを無視します。 これらのメンバーは、エラーコードを変更せず、一部のプラットフォーム呼び出しメソッドの呼び出しが成功したかどうかを判断するのに役立ちます。

- <xref:System.IntPtr.Zero?displayProperty=fullName>

- <xref:System.IntPtr.op_Equality%2A?displayProperty=fullName>

- <xref:System.IntPtr.op_Inequality%2A?displayProperty=fullName>

- <xref:System.Runtime.InteropServices.SafeHandle.IsInvalid%2A?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、プラットフォーム呼び出しメソッド<xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>の呼び出しの直後になるように、呼び出しをに移動します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
プラットフォーム呼び出しメソッドの呼び出しと<xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>メソッドの呼び出しの間のコードが明示的にまたは暗黙的にエラーコードを変更することができない場合は、この規則からの警告を抑制することが安全です。

## <a name="example"></a>例
次の例は、規則に違反するメソッドと、規則を満たすメソッドを示しています。

[!code-vb[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/VisualBasic/ca1404-call-getlasterror-immediately-after-p-invoke_1.vb)]
[!code-csharp[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/CSharp/ca1404-call-getlasterror-immediately-after-p-invoke_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA1060P/Invoke を NativeMethods クラスに移動する](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)

[CA1400P/Invoke エントリポイントが存在する必要があります](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)

[CA1401P/Invoke は表示されません](../code-quality/ca1401-p-invokes-should-not-be-visible.md)

[CA2101P/Invoke 文字列引数のマーシャリングを指定します](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)

[CA2205Win32 API のマネージドに相当するものを使用する](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)