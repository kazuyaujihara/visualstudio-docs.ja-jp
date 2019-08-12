---
title: CA1306:データ型のロケールを設定します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1306
- SetLocaleForDataTypes
helpviewer_keywords:
- CA1306
- SetLocaleForDataTypes
ms.assetid: 104297b2-5806-4de0-a8d9-c589380a796c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 893844741c848bee759f56dd027c9976a21902e8
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922785"
---
# <a name="ca1306-set-locale-for-data-types"></a>CA1306:データ型のロケールを設定します

|||
|-|-|
|TypeName|SetLocaleForDataTypes|
|CheckId|CA1306|
|カテゴリ|Microsoft のグローバリゼーション|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
メソッドまたはコンストラクターによって 1 <xref:System.Data.DataTable?displayProperty=fullName>つ<xref:System.Data.DataSet?displayProperty=fullName>以上のインスタンスが作成され、locale プロパティ<xref:System.Data.DataTable.Locale%2A?displayProperty=fullName> ( <xref:System.Data.DataSet.Locale%2A?displayProperty=fullName>または) が明示的に設定されていませんでした。

## <a name="rule-description"></a>規則の説明
ロケールによって、データのカルチャ固有のプレゼンテーション要素が決定されます。たとえば、数値、通貨記号、および並べ替え順序に使用する書式設定などです。 <xref:System.Data.DataTable>または<xref:System.Data.DataSet>を作成する場合は、ロケールを明示的に設定する必要があります。 既定では、これらの型のロケールは現在のカルチャです。 データベースまたはファイルに格納され、グローバルに共有されるデータの場合、ロケールは通常、インバリアントカルチャ (<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>) に設定する必要があります。 データがカルチャ間で共有されている場合、既定のロケールを使用<xref:System.Data.DataTable>する<xref:System.Data.DataSet>と、またはの内容が正しく表示されたり解釈されたりする可能性があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するに<xref:System.Data.DataTable>は、または<xref:System.Data.DataSet>のロケールを明示的に設定します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
ライブラリまたはアプリケーションが限定されたローカルユーザーを対象としている場合、データが共有されていない場合、または既定の設定により、サポートされているすべてのシナリオで望ましい動作が得られる場合は、この規則からの警告を抑制することが安全です。

## <a name="example"></a>例
次の例では<xref:System.Data.DataTable> 、2つのインスタンスを作成します。

[!code-csharp[FxCop.Globalization.DataTable#1](../code-quality/codesnippet/CSharp/ca1306-set-locale-for-data-types_1.cs)]

## <a name="see-also"></a>関連項目

- <xref:System.Data.DataTable?displayProperty=fullName>
- <xref:System.Data.DataSet?displayProperty=fullName>
- <xref:System.Globalization.CultureInfo?displayProperty=fullName>
- <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>
- <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>