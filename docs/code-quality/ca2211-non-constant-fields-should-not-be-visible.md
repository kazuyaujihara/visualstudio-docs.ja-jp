---
title: CA2211:非定数フィールドは表示されません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2211
- NonConstantFieldsShouldNotBeVisible
helpviewer_keywords:
- NonConstantFieldsShouldNotBeVisible
- CA2211
ms.assetid: e1e42c40-0acd-4312-af29-70133739a304
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 77909627385a7aa2e41f87c23ec41dc8ac0e1a5e
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920357"
---
# <a name="ca2211-non-constant-fields-should-not-be-visible"></a>CA2211:非定数フィールドは表示されません

|||
|-|-|
|TypeName|NonConstantFieldsShouldNotBeVisible|
|CheckId|CA2211|
|Category|Microsoft.Usage|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
パブリックまたはプロテクト静的フィールドは定数ではなく、読み取り専用です。

## <a name="rule-description"></a>規則の説明
定数でも読み取り専用でもない静的フィールドは、スレッド セーフではありません。 このようなフィールドへのアクセスは慎重に制御する必要があり、クラスオブジェクトへのアクセスを同期するための高度なプログラミング手法が必要です。 これらは習得して習得するのが困難であるため、このようなオブジェクトをテストすることで独自の課題が生じます。静的フィールドは、変更されないデータを格納するために最適に使用されます。 このルールは、ライブラリに適用されます。アプリケーションでは、フィールドを公開しないでください。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、静的フィールドを定数または読み取り専用にします。 これが不可能な場合は、基になるフィールドへのスレッドセーフなアクセスを管理するスレッドセーフなプロパティなど、別のメカニズムを使用するように型を再設計してください。 ロックの競合やデッドロックなどの問題が、ライブラリのパフォーマンスと動作に影響を与える可能性があることに注意してください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
アプリケーションを開発していて、静的フィールドを含む型へのアクセスを完全に制御できる場合は、この規則による警告を抑制することが安全です。 ライブラリデザイナーは、このルールからの警告を抑制しないでください。非定数の静的フィールドを使用すると、開発者が適切に使用するためにライブラリを使用することが難しくなります。

## <a name="example"></a>例
次の例は、この規則に違反する型を示しています。

[!code-vb[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/VisualBasic/ca2211-non-constant-fields-should-not-be-visible_1.vb)]
[!code-csharp[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/CSharp/ca2211-non-constant-fields-should-not-be-visible_1.cs)]