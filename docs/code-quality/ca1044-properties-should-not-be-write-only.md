---
title: CA1044:プロパティを書き込み専用にすることはできません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- PropertiesShouldNotBeWriteOnly
- CA1044
helpviewer_keywords:
- CA1044
- PropertiesShouldNotBeWriteOnly
ms.assetid: 8386bf3a-b161-4841-bf8b-92591595aea9
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 374bc4e9252dc07bde1f056aaf542811953fd69d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62778810"
---
# <a name="ca1044-properties-should-not-be-write-only"></a>CA1044:プロパティを書き込み専用にすることはできません

|||
|-|-|
|TypeName|PropertiesShouldNotBeWriteOnly|
|CheckId|CA1044|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

プロパティは、set アクセサーが get アクセサーではありませんが。

既定では、このルールのみが検索でパブリックの型が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

取得アクセサー プロパティへの読み取りアクセスを提供し、set アクセサーが書き込みアクセス権を提供します。 読み取り専用のプロパティは許容され、必要な場合もよくありますが、書き込み専用のプロパティを使用することはデザインのガイドラインで禁止されています。 これは、値を設定するためから値を表示し、ユーザーが原因では、セキュリティは提供されません。 また、読み取りアクセスがないと、共有オブジェクトのステータスを参照できないため、実用性が制限されます。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、プロパティに get アクセサーを追加します。 または、書き込み専用プロパティの動作が必要な場合は、このプロパティをメソッドに変換することを検討します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

このルールからの警告を抑制しないでくださいをお勧めします。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1044.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (デザイン) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="example"></a>例

次の例では、`BadClassWithWriteOnlyProperty`は書き込み専用プロパティを持つ型。 `GoodClassWithReadWriteProperty` 修正後のコードが含まれています。

[!code-vb[FxCop.Design.PropertiesNotWriteOnly#1](../code-quality/codesnippet/VisualBasic/ca1044-properties-should-not-be-write-only_1.vb)]
[!code-csharp[FxCop.Design.PropertiesNotWriteOnly#1](../code-quality/codesnippet/CSharp/ca1044-properties-should-not-be-write-only_1.cs)]