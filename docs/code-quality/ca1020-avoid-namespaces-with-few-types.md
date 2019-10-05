---
title: CA1020:型をほとんど含まない名前空間を使用しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
helpviewer_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
ms.assetid: 9cb272f6-a3ff-45af-b35d-70dea620b074
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6e5c50f607253304b05dd7ab9350646a0df05e70
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236237"
---
# <a name="ca1020-avoid-namespaces-with-few-types"></a>CA1020:型をほとんど含まない名前空間を使用しません

|||
|-|-|
|TypeName|AvoidNamespacesWithFewTypes|
|CheckId|CA1020|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

グローバル名前空間以外の名前空間に含まれる型が5つ未満です。

## <a name="rule-description"></a>規則の説明

各名前空間に論理組織があること、および少ないに設定された名前空間に型を配置するための有効な理由が存在することを確認します。 名前空間には、ほとんどのシナリオで一緒に使用される型が含まれている必要があります。 アプリケーションが相互に排他的な場合は、型を別の名前空間に配置する必要があります。 たとえば<xref:System.Web.UI> 、名前空間には、web アプリケーション<xref:System.Windows.Forms>で使用される型が含まれています。名前空間[!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)]には、ベースのアプリケーションで使用される型が含まれています。 両方の名前空間にユーザーインターフェイスの側面を制御する型がある場合でも、これらの型は同じアプリケーションで使用するように設計されていません。 そのため、これらは別々の名前空間に配置されます。 また、機能を見つけやすくするため、名前空間を慎重に編成することも役立ちます。 名前空間の階層を調べることで、ライブラリコンシューマーは、機能を実装する型を見つけることができます。

> [!NOTE]
> このガイドラインに準拠するには、デザイン時の型とアクセス許可を他の名前空間にマージしないでください。 これらの型は、メイン名前空間の下の独自の名前空間に属して`.Design`おり`.Permissions`、名前空間はそれぞれとで終了する必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、少数の型のみを含む名前空間を1つの名前空間に結合してみてください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

名前空間に他の名前空間の型と共に使用される型が含まれていない場合は、この規則からの警告を抑制することが安全です。