---
title: CA2004:GC.KeepAlive への呼び出しを削除します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4520649050e6e4004b2c8864d5c081897852826c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62808367"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004:GC.KeepAlive への呼び出しを削除します

|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|カテゴリ|Microsoft.Reliability|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 クラスの使用`SafeHandle`への呼び出しがまだ含まれているが`GC.KeepAlive`します。

## <a name="rule-description"></a>規則の説明
 変換する場合`SafeHandle`使用状況、呼び出しをすべて削除`GC.KeepAlive`(オブジェクト)。 この場合は、クラス必要はありませんを呼び出す`GC.KeepAlive`、ファイナライザーはありませんが、依存するいると仮定すると`SafeHandle`して OS ハンドルを完了します。  呼び出しで保持するためのコスト`GC.KeepAlive`ごくわずかであり、パフォーマンスの認識によって測定される場合がありますがへの呼び出し`GC.KeepAlive`必要であるか、または有効期間がコードになりますが困難になりますが、存在しなくなった問題を解決するためには維持します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 呼び出しを削除`GC.KeepAlive`します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。
 変換する技術的には位置が正しくない場合にのみ、この警告を抑制できます`SafeHandle`クラスで使用します。