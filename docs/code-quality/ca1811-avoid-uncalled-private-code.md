---
title: CA1811:呼び出されていないプライベート コードを使用しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidUncalledPrivateCode
- CA1811
helpviewer_keywords:
- CA1811
- AvoidUncalledPrivateCode
ms.assetid: aadbba74-7821-475f-8980-34d17c0a0a8b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 92a7542499eceeccbd62ce327b386dc099b726b2
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233619"
---
# <a name="ca1811-avoid-uncalled-private-code"></a>CA1811:呼び出されていないプライベート コードを使用しません

|||
|-|-|
|TypeName|AvoidUncalledPrivateCode|
|CheckId|CA1811|
|カテゴリ|Microsoft.Performance|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
プライベートまたは内部 (アセンブリレベル) のメンバーは、アセンブリ内の呼び出し元を持っていません。共通言語ランタイムによって呼び出されず、デリゲートによって呼び出されません。 次のメンバーは、この規則によってチェックされません。

- 明示的なインターフェイスメンバー。

- 静的コンストラクター。

- シリアル化コンストラクター。

- または<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>でマークされたメソッド。

- オーバーライドされるメンバー。

## <a name="rule-description"></a>規則の説明
このルールは、ルールロジックで現在識別されていないエントリポイントが発生した場合に、偽陽性を報告できます。 また、コンパイラが呼び出し不可能なコードをアセンブリに出力する場合もあります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、呼び出し不可能なコードを削除するか、それを呼び出すコードを追加します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
このルールからの警告を抑制するのは安全です。

## <a name="related-rules"></a>関連するルール
[CA1812インスタンス内部クラスを回避する](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

[CA1801使用されていないパラメーターの確認](../code-quality/ca1801-review-unused-parameters.md)

[CA1804未使用のローカルの削除](../code-quality/ca1804-remove-unused-locals.md)