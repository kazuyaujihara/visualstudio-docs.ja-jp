---
title: 'CA1301: アクセラレータが重複しないようにします。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1301
- AvoidDuplicateAccelerators
helpviewer_keywords:
- CA1301
- AvoidDuplicateAccelerators
ms.assetid: 20570a00-864b-459c-a1fa-a6e9db5f1001
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 647fef2968971cddb6a14cc19e53eed979b9c151
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661517"
---
# <a name="ca1301-avoid-duplicate-accelerators"></a>CA1301: アクセラレータが重複しないようにします
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidDuplicateAccelerators|
|CheckId|CA1301|
|カテゴリ|Microsoft のグローバリゼーション|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 型は <xref:System.Windows.Forms.Control?displayProperty=fullName> を拡張し、リソースファイルに格納されているのと同じアクセスキーを持つ、2つ以上のトップレベルコントロールを含みます。

## <a name="rule-description"></a>規則の説明
 Alt キーを使用するアクセス キー (アクセラレータとも呼ばれます) によって、キーボードからコントロールにアクセスできます。 アクセス キーの重複したコントロールがあると、アクセス キーの動作は不明確になります。 ユーザーは、アクセスキーを使用して目的のコントロールにアクセスできない可能性があります。また、有効になっている可能性のあるコントロール以外のコントロールにもアクセスできない可能性があります。

 このルールの現在の実装では、メニュー項目が無視されます。 ただし、同じサブメニュー内のメニュー項目は、同じアクセスキーを持つことはできません。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、すべてのコントロールに対して一意のアクセスキーを定義します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例は、同じアクセスキーを持つ2つのコントロールを含む、最小のフォームを示しています。 キーは、表示されないリソースファイルに格納されています。ただし、それらの値は、コメントアウトされた `checkBox.Text` 行に表示されます。 重複するアクセラレータの動作は、`checkBox.Text` の行をコメントアウトされたものと交換することによって調べることができます。 ただし、この例では、ルールから警告が生成されません。

 [!code-csharp[FxCop.Globalization.AvoidDuplicateAccels#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.AvoidDuplicateAccels/cs/FxCop.Globalization.AvoidDuplicateAccels.cs#1)]

## <a name="see-also"></a>参照
 [デスクトップアプリでのリソースの](https://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890)<xref:System.Resources.ResourceManager?displayProperty=fullName>
