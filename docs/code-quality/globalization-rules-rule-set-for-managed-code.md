---
title: マネージド コードの "グローバリゼーション規則" 規則セット
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 3c4032ee-0805-4581-8c48-b1827cd6b213
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: b81c27e22abc9034f417db4f2ddc9c84d54a0410
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72649538"
---
# <a name="globalization-rules-rule-set-for-managed-code"></a>マネージド コードの "グローバリゼーション規則" 規則セット

Microsoft グローバリゼーションルールのルールセットを使用して、アプリケーションのデータが異なる言語、ロケール、およびカルチャで正しく表示されない可能性のある問題に焦点を当てます。 アプリケーションがローカライズ、グローバル化、またはその両方である場合は、この規則セットを含める必要があります。

|規則|説明|
|----------|-----------------|
|[CA1300](../code-quality/ca1300.md)|MessageBoxOption を指定します|
|[CA1301](../code-quality/ca1301.md)|重複するアクセラレータを使用しません|
|[CA1302](../code-quality/ca1302.md)|ロケール固有の文字列をハードコーディングしない|
|[CA1303](../code-quality/ca1303.md)|ローカライズされるパラメーターとしてリテラルを渡さない|
|[CA1304](../code-quality/ca1304.md)|CultureInfo を指定します|
|[CA1305](../code-quality/ca1305.md)|IFormatProvider を指定します|
|[CA1306](../code-quality/ca1306.md)|データ型のロケールを設定します|
|[CA1307](../code-quality/ca1307.md)|StringComparison の指定|
|[CA1308](../code-quality/ca1308.md)|文字列を大文字に標準化します|
|[CA1309](../code-quality/ca1309.md)|順序を示す StringComparison を使用します|
|[CA2101](../code-quality/ca2101.md)|P/Invoke 文字列引数に対してマーシャリングを指定します|
