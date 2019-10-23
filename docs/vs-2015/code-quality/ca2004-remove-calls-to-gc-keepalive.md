---
title: 'CA2004: GC の呼び出しを削除します。KeepAlive |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: e34a8e7d4860a599155554410e13df5a6eb3bfe1
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672491"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: GC.KeepAlive への呼び出しを削除します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|カテゴリ|Microsoft.Reliability|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 クラスは `SafeHandle` を使用しますが、`GC.KeepAlive` の呼び出しを含みます。

## <a name="rule-description"></a>規則の説明
 @No__t_0 使用法に変換する場合は、`GC.KeepAlive` (object) へのすべての呼び出しを削除します。 この場合、クラスはファイナライザーを持たないものの、`SafeHandle` に依存してそれらの OS ハンドルを完了することを前提として、`GC.KeepAlive` を呼び出す必要はありません。  パフォーマンスによって測定されるように `GC.KeepAlive` を呼び出すことによるコストはごくわずかですが、`GC.KeepAlive` への呼び出しが必要か、または存在しなくなった可能性のある有効期間の問題を解決するのに十分であるという認識は、コードの保守が困難になります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 @No__t_0 の呼び出しを削除します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この警告が表示されないようにするには、クラス内の `SafeHandle` 使用法に変換するのが技術的に適切でない場合に限られます。
