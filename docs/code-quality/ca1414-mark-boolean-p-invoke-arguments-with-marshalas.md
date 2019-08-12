---
title: CA1414:ブール型の P/Invoke 引数を MarshalAs に設定します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
helpviewer_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
ms.assetid: c0c84cf5-7701-4897-9114-66fc4b895699
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 8e8d47b73009e0bd742c989ddc0311644453e5d9
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921864"
---
# <a name="ca1414-mark-boolean-pinvoke-arguments-with-marshalas"></a>CA1414:ブール型の P/Invoke 引数を MarshalAs に設定します

|||
|-|-|
|TypeName|MarkBooleanPInvokeArgumentsWithMarshalAs|
|CheckId|CA1414|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
プラットフォーム呼び出しメソッドの宣言に<xref:System.Boolean?displayProperty=fullName>パラメーターまたは戻り値が含まれています<xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName>が、パラメーターまたは戻り値に属性が適用されていません。

## <a name="rule-description"></a>規則の説明
プラットフォーム呼び出しメソッドはアンマネージコードにアクセスし、 `Declare` [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]またはの<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>キーワードを使用して定義されます。 <xref:System.Runtime.InteropServices.MarshalAsAttribute>マネージコードとアンマネージコードの間でデータ型を変換するために使用されるマーシャリング動作を指定します。 <xref:System.Byte?displayProperty=fullName> や<xref:System.Int32?displayProperty=fullName>などの多くの単純なデータ型は、アンマネージコードで1つの表現を持ち、マーシャリング動作の指定を必要としません。共通言語ランタイムは、自動的に正しい動作を提供します。

データ<xref:System.Boolean>型には、アンマネージコード内の複数の表現があります。 が指定されていない場合、 <xref:System.Boolean>データ型の既定のマーシャリング<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>動作はになります。 <xref:System.Runtime.InteropServices.MarshalAsAttribute> これは32ビットの整数であり、すべての状況に適しているわけではありません。 アンマネージメソッドによって必要とされるブール値は、適切な<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>に決定して照合する必要があります。 Unmanagedtype.bool は、常に4バイトの Win32 BOOL 型です。 またはその他の1バイトC++ `bool`型には unmanagedtype.bool を使用する必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、 <xref:System.Runtime.InteropServices.MarshalAsAttribute> <xref:System.Boolean>パラメーターまたは戻り値にを適用します。 属性の値を適切な<xref:System.Runtime.InteropServices.UnmanagedType>に設定します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。 既定のマーシャリング動作が適切な場合でも、動作が明示的に指定されていれば、コードをより簡単に管理できます。

## <a name="example"></a>例

次の例は、適切な<xref:System.Runtime.InteropServices.MarshalAsAttribute>属性でマークされたプラットフォーム呼び出しメソッドを示しています。

[!code-csharp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CSharp/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cs)]
[!code-vb[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/VisualBasic/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.vb)]
[!code-cpp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CPP/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cpp)]

## <a name="related-rules"></a>関連するルール
[CA1901P/Invoke 宣言はポータブルでなければなりません](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)

[CA2101P/Invoke 文字列引数のマーシャリングを指定します](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)

## <a name="see-also"></a>関連項目

- <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>
- [アンマネージ コードとの相互運用](/dotnet/framework/interop/index)