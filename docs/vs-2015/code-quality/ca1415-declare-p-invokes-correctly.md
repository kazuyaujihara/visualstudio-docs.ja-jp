---
title: 'CA1415: Declare P-正しく呼び出される |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 922cd713867e1e1017a0f13490a08c0950b2afbf
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652682"
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415: P/Invoke を正しく宣言します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DeclarePInvokesCorrectly|
|CheckId|CA1415|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|非互換性-パラメーターを宣言する P/Invoke がアセンブリの外部に表示されない場合。 中断-パラメーターを宣言する P/Invoke がアセンブリの外部に表示される可能性があります。|

## <a name="cause"></a>原因
 プラットフォーム呼び出しメソッドが正しく宣言されていません。

## <a name="rule-description"></a>規則の説明
 プラットフォーム呼び出しメソッドはアンマネージコードにアクセスし、[!INCLUDE[vbprvb](../includes/vbprvb-md.md)] または <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> の `Declare` キーワードを使用して定義されます。 現在、このルールでは、オーバーラップ構造のパラメーターへのポインターを持ち、対応するマネージパラメーターが <xref:System.Threading.NativeOverlapped?displayProperty=fullName> 構造体へのポインターではない、Win32 関数を対象とするプラットフォーム呼び出しメソッドの宣言を検索します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、プラットフォーム呼び出しメソッドを正しく宣言します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例は、規則に違反し、規則を満たすプラットフォーム呼び出しメソッドを示しています。

 [!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DeclarePInvokes/cs/FxCop.Interoperability.DeclarePInvokes.cs#1)]

## <a name="see-also"></a>参照
 [アンマネージ コードとの相互運用](https://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)
