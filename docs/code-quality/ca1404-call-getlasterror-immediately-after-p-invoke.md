---
title: 'CA1404: P-Invoke の直後に GetLastError を呼び出します'
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
ms.openlocfilehash: 6529adafa7384bf8b51444dd2cc81b9952b6b57c
ms.sourcegitcommit: 1507baf3a336bbb6511d4c3ce73653674831501b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72349021"
---
# <a name="ca1404-call-getlasterror-immediately-after-pinvoke"></a>CA1404: P/Invoke の直後に GetLastError を呼び出します

|||
|-|-|
|TypeName|CallGetLastErrorImmediatelyAfterPInvoke|
|CheckId|CA1404|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

@No__t-0 メソッドまたは同等の Win32 `GetLastError` 関数への呼び出しが行われ、その直前にある呼び出しがプラットフォーム呼び出しメソッドになりません。

## <a name="rule-description"></a>規則の説明
プラットフォーム呼び出しメソッドはアンマネージコードにアクセスし、[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] または <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 属性の @no__t 0 キーワードを使用して定義されます。 一般に、エラーが発生した場合、アンマネージ関数は Win32 `SetLastError` 関数を呼び出して、エラーに関連付けられているエラーコードを設定します。 失敗した関数の呼び出し元は、Win32 `GetLastError` 関数を呼び出してエラーコードを取得し、エラーの原因を特定します。 エラーコードはスレッドごとに保持され、次に @no__t を呼び出したときに上書きされます。 失敗したプラットフォーム呼び出しメソッドを呼び出した後、マネージコードは <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> メソッドを呼び出すことによってエラーコードを取得できます。 エラーコードは、他のマネージクラスライブラリメソッドからの内部呼び出しによって上書きされる可能性があるため、`GetLastError` または <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> メソッドは、プラットフォーム呼び出しメソッドの呼び出しの直後に呼び出す必要があります。

このルールは、platform invoke メソッドの呼び出しと <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> への呼び出しの間に発生した場合に、次のマネージメンバーへの呼び出しを無視します。 これらのメンバーは、エラーコードを変更せず、一部のプラットフォーム呼び出しメソッドの呼び出しが成功したかどうかを判断するのに役立ちます。

- <xref:System.IntPtr.Zero?displayProperty=fullName>

- <xref:System.IntPtr.op_Equality%2A?displayProperty=fullName>

- <xref:System.IntPtr.op_Inequality%2A?displayProperty=fullName>

- <xref:System.Runtime.InteropServices.SafeHandle.IsInvalid%2A?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、プラットフォーム呼び出しメソッドの呼び出しの直後になるように <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> への呼び出しを移動します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
Platform invoke メソッド呼び出しと <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> メソッド呼び出しの間のコードが明示的または暗黙的にエラーコードを変更することができない場合は、この規則からの警告を抑制することが安全です。

## <a name="example"></a>例
次の例は、規則に違反するメソッドと、規則を満たすメソッドを示しています。

[!code-vb[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/VisualBasic/ca1404-call-getlasterror-immediately-after-p-invoke_1.vb)]
[!code-csharp[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/CSharp/ca1404-call-getlasterror-immediately-after-p-invoke_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA1060: P/Invoke を NativeMethods クラスに移動します](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)

[CA1400: P/Invoke エントリ ポイントは存在しなければなりません](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)

[CA1401: P/Invoke は参照可能になりません](../code-quality/ca1401-p-invokes-should-not-be-visible.md)

[CA2101: P/Invoke 文字列引数に対してマーシャリングを指定します](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)

[CA2205: Win32 API に相当するマネージド API を使用します](../code-quality/ca2205.md)