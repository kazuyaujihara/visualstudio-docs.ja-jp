---
title: 'CA1410: COM 登録メソッドは一致しなければなりません |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
helpviewer_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 30f507f07de858dc222b4824ac6da633c76812ab
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652745"
---
# <a name="ca1410-com-registration-methods-should-be-matched"></a>CA1410: COM 登録メソッドは一致しなければなりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ComRegistrationMethodsShouldBeMatched|
|CheckId|CA1410|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 型は、<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 属性でマークされたメソッドを宣言していますが、<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> 属性でマークされたメソッドを宣言していません。または、その逆も同様です。

## <a name="rule-description"></a>規則の説明
 コンポーネントオブジェクトモデル (COM) クライアントで [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 型を作成するには、その型を最初に登録する必要があります。 使用可能な場合は、ユーザー指定のコードを実行するための登録プロセス中に、<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> 属性でマークされたメソッドが呼び出されます。 @No__t_0 属性でマークされた対応するメソッドは、登録メソッドの操作を元に戻すための登録解除プロセス中に呼び出されます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、対応する登録または登録解除の方法を追加します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例は、規則に違反する型を示しています。 コメント化されたコードは、違反の修正を示しています。

 [!code-csharp[FxCop.Interoperability.ComRegistration#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComRegistration/cs/FxCop.Interoperability.ComRegistration.cs#1)]
 [!code-vb[FxCop.Interoperability.ComRegistration#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComRegistration/vb/FxCop.Interoperability.ComRegistration.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA1411: COM 登録メソッドは参照可能であることはできません](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)

## <a name="see-also"></a>参照
 [アセンブリを COM regasm.exe に登録](https://msdn.microsoft.com/library/87925795-a3ae-4833-b138-125413478551)<xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName> [(アセンブリ登録ツール)](https://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb)
