---
title: 'CA2212: サービスコンポーネントに WebMethod | を設定しません。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
helpviewer_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
ms.assetid: 774bc55d-e588-48ee-8f38-c228580feca2
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 2ee166f8bbc14e66968cd4f7c265331854905ac9
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72662945"
---
# <a name="ca2212-do-not-mark-serviced-components-with-webmethod"></a>CA2212: サービス コンポーネントを WebMethod に設定しません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotMarkServicedComponentsWithWebMethod|
|CheckId|CA2212|
|カテゴリ|Microsoft. 使用方法|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 @No__t_0 から継承する型のメソッドは、<xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName> でマークされます。

## <a name="rule-description"></a>規則の説明
 <xref:System.Web.Services.WebMethodAttribute> は、ASP.NET を使用して作成された XML Web サービス内のメソッドに適用されます。これにより、メソッドがリモート Web クライアントから呼び出すことができるようになります。 メソッドとクラスはパブリックであり、ASP.NET Web アプリケーションで実行されている必要があります。 <xref:System.EnterpriseServices.ServicedComponent> 型は COM + アプリケーションによってホストされ、COM + サービスを使用できます。 <xref:System.Web.Services.WebMethodAttribute> は、同じシナリオを想定していないため、<xref:System.EnterpriseServices.ServicedComponent> の型には適用されません。 具体的には、<xref:System.EnterpriseServices.ServicedComponent> メソッドに属性を追加しても、リモート Web クライアントからメソッドを呼び出すことはできません。 @No__t_0 と <xref:System.EnterpriseServices.ServicedComponent> メソッドには、コンテキストとトランザクションフローの動作と要件が競合しているため、メソッドの動作は、一部のシナリオでは正しくありません。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、<xref:System.EnterpriseServices.ServicedComponent> メソッドから属性を削除します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。 これらの要素を組み合わせた方が正しいシナリオはありません。

## <a name="see-also"></a>参照
 <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName> <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>
