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
ms.openlocfilehash: 99274abee2c05a1bd33e34c9eb02cc928c1b54b0
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234613"
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415:P/Invoke を正しく宣言します

|||
|-|-|
|TypeName|DeclarePInvokesCorrectly|
|CheckId|CA1415|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|非互換性-パラメーターを宣言する P/Invoke がアセンブリの外部に表示されない場合。 中断-パラメーターを宣言する P/Invoke がアセンブリの外部に表示される可能性があります。|

## <a name="cause"></a>原因
プラットフォーム呼び出しメソッドが正しく宣言されていません。

## <a name="rule-description"></a>規則の説明
プラットフォーム呼び出しメソッドはアンマネージコードにアクセスし、 `Declare` [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]またはの<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>キーワードを使用して定義されます。 現在、このルールでは、オーバーラップ構造パラメーターへのポインターを持ち、対応するマネージパラメーターが<xref:System.Threading.NativeOverlapped?displayProperty=fullName>構造体へのポインターではない Win32 関数を対象とするプラットフォーム呼び出しメソッドの宣言を検索します。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、プラットフォーム呼び出しメソッドを正しく宣言します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、規則に違反し、規則を満たすプラットフォーム呼び出しメソッドを示しています。

[!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../code-quality/codesnippet/CSharp/ca1415-declare-p-invokes-correctly_1.cs)]

## <a name="see-also"></a>関連項目
[アンマネージ コードとの相互運用](/dotnet/framework/interop/index)