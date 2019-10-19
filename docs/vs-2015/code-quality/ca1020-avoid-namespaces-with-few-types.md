---
title: 'CA1020: いくつかの型の名前空間を使用しないでください |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
helpviewer_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
ms.assetid: 9cb272f6-a3ff-45af-b35d-70dea620b074
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 81eaf2735869668b86ca8879478e3d76d77a2811
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72662310"
---
# <a name="ca1020-avoid-namespaces-with-few-types"></a>CA1020: 型をほとんど含まない名前空間を使用しません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidNamespacesWithFewTypes|
|CheckId|CA1020|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 グローバル名前空間以外の名前空間に含まれる型が5つ未満です。

## <a name="rule-description"></a>規則の説明
 各名前空間に論理組織があること、および少ないに設定された名前空間に型を配置するための有効な理由が存在することを確認します。 名前空間には、ほとんどのシナリオで一緒に使用される型が含まれている必要があります。 アプリケーションが相互に排他的な場合は、型を別の名前空間に配置する必要があります。 たとえば、<xref:System.Web.UI> 名前空間には、Web アプリケーションで使用される型が含まれています。また、<xref:System.Windows.Forms> 名前空間には、[!INCLUDE[TLA#tla_mswin](../includes/tlasharptla-mswin-md.md)] ベースのアプリケーションで使用される型が含まれています。 両方の名前空間にユーザーインターフェイスの側面を制御する型がある場合でも、これらの型は同じアプリケーションで使用するように設計されていません。 そのため、これらは別々の名前空間に配置されます。 また、機能を見つけやすくするため、名前空間を慎重に編成することも役立ちます。 名前空間の階層を調べることで、ライブラリコンシューマーは、機能を実装する型を見つけることができます。

> [!NOTE]
> このガイドラインに準拠するには、デザイン時の型とアクセス許可を他の名前空間にマージしないでください。 これらの型は、メインの名前空間の下の独自の名前空間に属しており、名前空間はそれぞれ `.Design` と `.Permissions` で終了する必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、少数の型のみを含む名前空間を1つの名前空間に結合してみてください。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 名前空間に他の名前空間の型と共に使用される型が含まれていない場合は、この規則からの警告を抑制することが安全です。
