---
title: CA2212:サービス コンポーネントを WebMethod に設定しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
helpviewer_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
ms.assetid: 774bc55d-e588-48ee-8f38-c228580feca2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7b2ace5f6e51fc7a8d29faab14cc2332fd808f93
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231651"
---
# <a name="ca2212-do-not-mark-serviced-components-with-webmethod"></a>CA2212:サービス コンポーネントを WebMethod に設定しません

|||
|-|-|
|TypeName|DoNotMarkServicedComponentsWithWebMethod|
|CheckId|CA2212|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

から<xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName>継承される型のメソッドは、で<xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>マークされます。

## <a name="rule-description"></a>規則の説明

<xref:System.Web.Services.WebMethodAttribute>ASP.NET を使用して作成された XML web サービス内のメソッドに適用されます。これにより、メソッドがリモート web クライアントから呼び出すことができるようになります。 メソッドとクラスはパブリックであり、ASP.NET web アプリケーションで実行されている必要があります。 <xref:System.EnterpriseServices.ServicedComponent>型は COM + アプリケーションによってホストされ、COM + サービスを使用できます。 <xref:System.Web.Services.WebMethodAttribute>は、同じシナリオ<xref:System.EnterpriseServices.ServicedComponent>を想定していないため、型には適用されません。 具体的には、 <xref:System.EnterpriseServices.ServicedComponent>メソッドに属性を追加しても、リモート web クライアントからメソッドを呼び出すことはできません。 とメソッドにはコンテキストおよびトランザクションフローの動作と要件が競合しているため<xref:System.Web.Services.WebMethodAttribute> 、メソッドの動作は一部のシナリオでは正しくありません。 <xref:System.EnterpriseServices.ServicedComponent>

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、 <xref:System.EnterpriseServices.ServicedComponent>メソッドから属性を削除します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。 これらの要素を組み合わせた方が正しいシナリオはありません。

## <a name="see-also"></a>関連項目

- <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName>
- <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>