---
title: CA1415:P/Invoke を正しく宣言します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: da6448a414437a07b545a999b35031f82e9a8689
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546187"
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415:P/Invoke を正しく宣言します

|||
|-|-|
|TypeName|DeclarePInvokesCorrectly|
|CheckId|CA1415|
|カテゴリ|Microsoft.Interoperability|
|互換性に影響する変更点|非的な P/invoke パラメーターを宣言する場合は、アセンブリの外部表示できません。 あり - 場合は、アセンブリの外部パラメーターを宣言する P/invoke を確認できます。|

## <a name="cause"></a>原因
 プラットフォーム呼び出しメソッド宣言が正しくありません。

## <a name="rule-description"></a>規則の説明
 プラットフォームがメソッドへのアクセスのアンマネージ コードを呼び出すし、によって定義されている、`Declare`キーワード[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]または<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>します。 現時点では、このルールは、プラットフォーム呼び出しメソッドの宣言を OVERLAPPED 構造体パラメーターへのポインターを持つ Win32 関数を対象とすると、対応するマネージ型のパラメーターがないへのポインターを検索、<xref:System.Threading.NativeOverlapped?displayProperty=fullName>構造体。

## <a name="how-to-fix-violations"></a>違反の修正方法
 このルールの違反を修正するには、プラットフォームを正しく宣言メソッドを呼び出します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例はプラットフォームが、規則に違反して、規則に適合するメソッドを呼び出します。

 [!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../code-quality/codesnippet/CSharp/ca1415-declare-p-invokes-correctly_1.cs)]

## <a name="see-also"></a>関連項目
 [アンマネージ コードとの相互運用](/dotnet/framework/interop/index)