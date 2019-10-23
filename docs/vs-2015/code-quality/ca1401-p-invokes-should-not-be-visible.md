---
title: 'CA1401: P-Invoke を visible にすることはできません。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PInvokesShouldNotBeVisible
- CA1401
helpviewer_keywords:
- CA1401
- PInvokesShouldNotBeVisible
ms.assetid: 0f4d96c1-f9de-414e-b223-4dc7f691bee3
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: f3f867f14f7a2eca4482f1f8d5fb48149f02f43f
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661356"
---
# <a name="ca1401-pinvokes-should-not-be-visible"></a>CA1401: P/Invoke は参照可能になりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|PInvokesShouldNotBeVisible|
|CheckId|CA1401|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 パブリック型のパブリックメソッドまたはプロテクトメソッドには、<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 属性があります ([!INCLUDE[vbprvb](../includes/vbprvb-md.md)] の `Declare` キーワードによっても実装されます)。

## <a name="rule-description"></a>規則の説明
 @No__t_0 属性 (または [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] で `Declare` キーワードを使用して定義されているメソッド) でマークされたメソッドは、プラットフォーム呼び出しサービスを使用してアンマネージコードにアクセスします。 このようなメソッドは公開しないでください。 これらのメソッドをプライベートまたは内部として保持することにより、他の方法で呼び出すことができなかったアンマネージ Api に呼び出し元がアクセスできるようにすることで、ライブラリを使用してセキュリティを侵害できるようにすることができます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、メソッドのアクセスレベルを変更します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例では、この規則に違反するメソッドを宣言しています。

 [!code-csharp[FxCop.Interoperability.DllImports#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DllImports/cs/FxCop.Interoperability.DllImports.cs#1)]
 [!code-vb[FxCop.Interoperability.DllImports#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DllImports/vb/FxCop.Interoperability.DllImports.vb#1)]
