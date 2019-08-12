---
title: CA1823:使用されていないプライベート フィールドを使用しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidUnusedPrivateFields
- CA1823
helpviewer_keywords:
- AvoidUnusedPrivateFields
- CA1823
ms.assetid: 614f94f6-0dc7-430f-8124-cb889a4a720f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 47a2ad3b64055584551a63a2333e29286783d8cf
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921356"
---
# <a name="ca1823-avoid-unused-private-fields"></a>CA1823:使用されていないプライベート フィールドを使用しません

|||
|-|-|
|TypeName|AvoidUnusedPrivateFields|
|CheckId|CA1823|
|Category|Microsoft.Performance|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
このルールは、コード内のプライベートフィールドが存在するが、どのコードパスでも使用されていない場合に報告されます。

## <a name="rule-description"></a>規則の説明
アセンブリ内でアクセスされていないと思われるプライベート フィールドが検出されました。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、フィールドを削除するか、そのフィールドを使用するコードを追加します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
このルールからの警告を抑制するのは安全です。

## <a name="related-rules"></a>関連するルール
[CA1812インスタンス内部クラスを回避する](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

[CA1801使用されていないパラメーターの確認](../code-quality/ca1801-review-unused-parameters.md)

[CA1804未使用のローカルの削除](../code-quality/ca1804-remove-unused-locals.md)

[CA1811呼び出されるプライベートコードを避ける](../code-quality/ca1811-avoid-uncalled-private-code.md)