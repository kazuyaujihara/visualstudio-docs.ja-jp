---
title: 'CA1306: データ型のロケールを設定する |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1306
- SetLocaleForDataTypes
helpviewer_keywords:
- CA1306
- SetLocaleForDataTypes
ms.assetid: 104297b2-5806-4de0-a8d9-c589380a796c
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 03344f0b19552aa00270c8a6fa760c6ba6ee75f4
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661416"
---
# <a name="ca1306-set-locale-for-data-types"></a>CA1306: データ型のロケールを設定します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|SetLocaleForDataTypes|
|CheckId|CA1306|
|カテゴリ|Microsoft のグローバリゼーション|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 メソッドまたはコンストラクターが1つ以上の <xref:System.Data.DataTable?displayProperty=fullName> インスタンスまたは <xref:System.Data.DataSet?displayProperty=fullName> インスタンスを作成し、locale プロパティ (<xref:System.Data.DataTable.Locale%2A?displayProperty=fullName> または <xref:System.Data.DataSet.Locale%2A?displayProperty=fullName>) を明示的に設定していませんでした。

## <a name="rule-description"></a>規則の説明
 ロケールによって、データのカルチャ固有のプレゼンテーション要素が決定されます。たとえば、数値、通貨記号、および並べ替え順序に使用する書式設定などです。 @No__t_0 または <xref:System.Data.DataSet> を作成する場合は、ロケールを明示的に設定する必要があります。 既定では、これらの型のロケールは現在のカルチャです。 データベースまたはファイルに格納され、グローバルに共有されているデータの場合は、通常、ロケールをインバリアントカルチャ (<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>) に設定する必要があります。 データがカルチャ間で共有されている場合、既定のロケールを使用すると、<xref:System.Data.DataTable> または <xref:System.Data.DataSet> の内容が正しく表示または解釈されない可能性があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、<xref:System.Data.DataTable> または <xref:System.Data.DataSet> のロケールを明示的に設定します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 ライブラリまたはアプリケーションが限定されたローカルユーザーを対象としている場合、データが共有されていない場合、または既定の設定により、サポートされているすべてのシナリオで望ましい動作が得られる場合は、この規則からの警告を抑制することが安全です。

## <a name="example"></a>例
 次の例では、2つの <xref:System.Data.DataTable> インスタンスを作成します。

 [!code-csharp[FxCop.Globalization.DataTable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.DataTable/cs/FxCop.Globalization.DataTable.cs#1)]

## <a name="see-also"></a>参照
 <xref:System.Data.DataTable?displayProperty=fullName> <xref:System.Data.DataSet?displayProperty=fullName>
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>
 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>
 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>
