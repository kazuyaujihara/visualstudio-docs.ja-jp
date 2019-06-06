---
title: CA2228:未公開のリソース形式を出荷しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5f8a672056c8663c2e27ec730e542083aee9738f
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "66714980"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228:未公開のリソース形式を出荷しません

|||
|-|-|
|TypeName|DoNotShipUnreleasedResourceFormats|
|CheckId|CA2228|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

リソース ファイルは、現在サポートされていない .NET のバージョンを使用して構築されました。

## <a name="rule-description"></a>規則の説明

プレリリース バージョンの .NET を使用して構築されたリソース ファイルは、サポートされているバージョンの .NET で使用できるしない場合があります。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、サポートされているバージョンの .NET を使用して、リソースをビルドします。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告は抑制しないでください。
