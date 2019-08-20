---
title: マネージド コードの "グローバリゼーション規則" 規則セット
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 3c4032ee-0805-4581-8c48-b1827cd6b213
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ffba6b69e1f67b369f3d99c1b54a88448df8a41b
ms.sourcegitcommit: b83fefa8177c5554cbe2c59c4d102cbc534f7cc6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69584984"
---
# <a name="globalization-rules-rule-set-for-managed-code"></a>マネージド コードの "グローバリゼーション規則" 規則セット

Microsoft グローバリゼーションルールのルールセットを使用して、アプリケーションのデータが異なる言語、ロケール、およびカルチャで正しく表示されない可能性のある問題に焦点を当てます。 アプリケーションがローカライズ、グローバル化、またはその両方である場合は、この規則セットを含める必要があります。

|ルール|説明|
|----------|-----------------|
|[CA1300](../code-quality/ca1300-specify-messageboxoptions.md)|MessageBoxOption を指定します|
|[CA1301](../code-quality/ca1301-avoid-duplicate-accelerators.md)|重複するアクセラレータを使用しません|
|[CA1302](../code-quality/ca1302-do-not-hardcode-locale-specific-strings.md)|ロケール固有の文字列をハードコーディングしない|
|[CA1303](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)|ローカライズされるパラメーターとしてリテラルを渡さない|
|[CA1304](../code-quality/ca1304-specify-cultureinfo.md)|CultureInfo を指定します|
|[CA1305](../code-quality/ca1305-specify-iformatprovider.md)|IFormatProvider を指定します|
|[CA1306](../code-quality/ca1306-set-locale-for-data-types.md)|データ型のロケールを設定します|
|[CA1307](../code-quality/ca1307-specify-stringcomparison.md)|StringComparison の指定|
|[CA1308](../code-quality/ca1308-normalize-strings-to-uppercase.md)|文字列を大文字に標準化します|
|[CA1309](../code-quality/ca1309-use-ordinal-stringcomparison.md)|順序を示す StringComparison を使用します|
|[CA2101](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)|P/Invoke 文字列引数に対してマーシャリングを指定します|