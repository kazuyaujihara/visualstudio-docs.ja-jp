---
title: CA1401:P/Invoke は参照可能になりません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PInvokesShouldNotBeVisible
- CA1401
helpviewer_keywords:
- CA1401
- PInvokesShouldNotBeVisible
ms.assetid: 0f4d96c1-f9de-414e-b223-4dc7f691bee3
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e26daf68e0031358605427b310bb7284d43baf1b
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922132"
---
# <a name="ca1401-pinvokes-should-not-be-visible"></a>CA1401:P/Invoke は参照可能であることはできません

|||
|-|-|
|TypeName|PInvokesShouldNotBeVisible|
|CheckId|CA1401|
|Category|Microsoft. 相互運用性|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
パブリック型のパブリックメソッドまたはプロテクトメソッドには<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 、属性があります ( `Declare`の[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]キーワードによっても実装されます)。

## <a name="rule-description"></a>規則の説明
<xref:System.Runtime.InteropServices.DllImportAttribute>属性 (またはで`Declare` [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]キーワードを使用して定義されているメソッド) でマークされたメソッドは、プラットフォーム呼び出しサービスを使用してアンマネージコードにアクセスします。 このようなメソッドは公開しないでください。 これらのメソッドをプライベートまたは内部として保持することにより、他の方法で呼び出すことができなかったアンマネージ Api に呼び出し元がアクセスできるようにすることで、ライブラリを使用してセキュリティを侵害できるようにすることができます。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、メソッドのアクセスレベルを変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例では、この規則に違反するメソッドを宣言しています。

[!code-vb[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/VisualBasic/ca1401-p-invokes-should-not-be-visible_1.vb)]
[!code-csharp[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/CSharp/ca1401-p-invokes-should-not-be-visible_1.cs)]