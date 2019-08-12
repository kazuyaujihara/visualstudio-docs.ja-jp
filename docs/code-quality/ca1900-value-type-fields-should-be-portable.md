---
title: CA1900:値型フィールドはポータブルでなければなりません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1900
- ValueTypeFieldsShouldBePortable
helpviewer_keywords:
- ValueTypeFieldsShouldBePortable
- CA1900
ms.assetid: 1787d371-389f-4d39-b305-12b53bc0dfb9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f734d0cf28a5aec28ebbf635dd384efe176b1774
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921316"
---
# <a name="ca1900-value-type-fields-should-be-portable"></a>CA1900:値型フィールドはポータブルでなければなりません

|||
|-|-|
|TypeName|ValueTypeFieldsShouldBePortable|
|CheckId|CA1900|
|Category|Microsoft. 移植性|
|互換性に影響する変更点|中断-フィールドがアセンブリの外部に表示されるかどうか。<br /><br /> 非互換性-フィールドがアセンブリの外部で参照できない場合。|

## <a name="cause"></a>原因
このルールでは、64ビットオペレーティングシステム上のアンマネージコードにマーシャリングするときに、明示的なレイアウトで宣言されている構造が正しく配置されていることを確認します。 IA-64 では、アライメントされていないメモリアクセスは許可されません。この違反が修正されない場合、プロセスはクラッシュします。

## <a name="rule-description"></a>規則の説明
ミスアライメントのあるフィールドを含む明示的なレイアウトを持つ構造体は、64ビットのオペレーティングシステムでクラッシュします。

## <a name="how-to-fix-violations"></a>違反の修正方法
8バイトより小さいすべてのフィールドには、そのサイズの倍数であるオフセットが必要です。また、8バイト以上のフィールドには、8の倍数であるオフセットが必要です。 もう1つの解決`LayoutKind.Sequential`策は`LayoutKind.Explicit`、の代わりにを使用することです (適切な場合)。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この警告は、エラーが発生した場合にのみ抑制する必要があります。