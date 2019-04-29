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
ms.openlocfilehash: a47b7e703d811ff5dce421db103af89bb3a76512
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62796437"
---
# <a name="ca2212-do-not-mark-serviced-components-with-webmethod"></a>CA2212:サービス コンポーネントを WebMethod に設定しません

|||
|-|-|
|TypeName|DoNotMarkServicedComponentsWithWebMethod|
|CheckId|CA2212|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

継承する型のメソッド<xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName>でマークされた<xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>します。

## <a name="rule-description"></a>規則の説明

<xref:System.Web.Services.WebMethodAttribute> ASP.NET; を使用して作成された XML web サービス内のメソッドに適用されます。これは、リモート web クライアントからメソッドを呼び出し可能にします。 メソッドとクラスは、パブリックにし、ASP.NET web アプリケーションで実行する必要があります。 <xref:System.EnterpriseServices.ServicedComponent> 種類は、COM + アプリケーションでホストされており、COM + サービスを使用することができます。 <xref:System.Web.Services.WebMethodAttribute> 適用されません<xref:System.EnterpriseServices.ServicedComponent>型同じシナリオに対する意図されていないためです。 具体的には、属性を追加する、<xref:System.EnterpriseServices.ServicedComponent>メソッドを行わない、メソッド呼び出し可能なリモートの web クライアントから。 <xref:System.Web.Services.WebMethodAttribute>と<xref:System.EnterpriseServices.ServicedComponent>メソッドがある動作が競合して、コンテキストとトランザクション フロー、メソッドの動作の要件は一部のシナリオでは不正確になります。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を解決するからの属性を削除、<xref:System.EnterpriseServices.ServicedComponent>メソッド。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告は抑制しないでください。 これらの要素を組み合わせることが適切であるシナリオではありません。

## <a name="see-also"></a>関連項目

- <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName>
- <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>